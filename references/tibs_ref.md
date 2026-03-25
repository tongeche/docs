Below is a **direct mapping: endpoint → tables → intent → notes**.
No abstraction.

---

# 1) REPORT FLOW (write)

## POST `/reports`

```id="map-reports"
TABLES:
- incident_reports
- incident_report_media
- reporter_location_samples
- vehicles (upsert if needed)
- saccos (via match function)
- routes

FLOW:
1. normalize plate
2. resolve sacco (match_sacco_name)
3. resolve route + corridor
4. insert incident_reports
5. attach media (optional)
6. store location sample
```

---

# 2) INCIDENTS (read - public)

## GET `/incidents/nearby`

```id="map-incidents-nearby"
TABLES:
- incident_map_feed
- incidents
- incident_types
- incident_categories
- incident_corridors

FILTER:
- by lat/lng
- by corridor
- by time window

RETURN:
- incident_id
- type
- severity
- location
- vehicle (if exists)
- confidence
```

---

## GET `/incidents/:id`

```id="map-incident-detail"
TABLES:
- incidents
- incident_reports
- incident_report_media
- incident_verifications
- incident_confidence_assessments

RETURN:
- full incident detail
- contributing reports
- media
- confidence score
```

---

# 3) VEHICLE LOOKUP

## GET `/vehicles/:plate`

```id="map-vehicle"
TABLES:
- vehicles
- vehicle_public_profiles
- vehicle_saccos
- vehicle_routes
- vehicle_score_summaries
- vehicle_weighted_score_summaries
- vehicle_incident_summaries

RETURN:
- plate
- sacco
- route
- risk score
- incident count
```

---

## GET `/vehicles/:id/incidents`

```id="map-vehicle-incidents"
TABLES:
- vehicle_incident_summaries
- incidents

RETURN:
- recent incidents
- severity
```

---

# 4) FEEDBACK

## POST `/feedback`

```id="map-feedback"
TABLES:
- ride_feedback
- ride_feedback_tag_links
- ride_feedback_media

FLOW:
- insert feedback
- attach tags
- attach media (optional)
```

---

## GET `/vehicles/:id/feedback-summary`

```id="map-feedback-summary"
TABLES:
- vehicle_feedback_public
- feedback_sentiments
- feedback_tags

RETURN:
- sentiment score
- common tags
```

---

# 5) CORRIDORS

## GET `/corridors`

```id="map-corridors"
TABLES:
- corridors
- corridor_public_overview
- corridor_score_summaries
- corridor_weighted_score_summaries

RETURN:
- id
- name
- risk score
```

---

## GET `/corridors/:id/incidents`

```id="map-corridor-incidents"
TABLES:
- incident_corridors
- incidents
- incident_map_feed

RETURN:
- incidents in corridor
```

---

# 6) ROUTES + SACCO

## GET `/routes`

```id="map-routes"
TABLES:
- routes
- route_corridors

RETURN:
- route name
- corridor mapping
```

---

## GET `/saccos`

```id="map-saccos"
TABLES:
- saccos
- sacco_score_summaries

RETURN:
- sacco name
- score
```

---

## GET `/saccos/:id/vehicles`

```id="map-sacco-vehicles"
TABLES:
- vehicle_saccos
- vehicles

RETURN:
- vehicles under sacco
```

---

# 7) SURVEYOR SYSTEM

## POST `/surveyor/session/start`

```id="map-session"
TABLES:
- surveyor_sessions
```

---

## GET `/surveyor/assignments`

```id="map-assignments"
TABLES:
- surveyor_route_assignments
- assignment_slots
```

---

## GET `/surveyor/stats`

```id="map-stats"
TABLES:
- surveyor_daily_work_summaries
```

---

# 8) LEARNING

## GET `/learning/courses`

```id="map-learning"
TABLES:
- learning_courses
- learning_modules
```

---

## GET `/learning/progress`

```id="map-learning-progress"
TABLES:
- learning_module_progress
- learning_course_enrollments
```

---

# 9) SEARCH (important for UX)

## GET `/search?q=`

```id="map-search"
TABLES:
- vehicles
- saccos
- sacco_aliases
- routes

FLOW:
1. normalize input
2. match vehicle
3. match sacco (alias + canonical)
4. match route

RETURN:
- mixed results
```

---

# 10) INTERNAL / ADMIN (restricted)

## GET `/admin/review-queue`

```id="map-admin"
TABLES:
- incident_review_queue
- incident_review_queue_view
```

---

## POST `/admin/review`

```id="map-review"
TABLES:
- incident_review_decisions
- incident_review_latest_decisions
```

---

# KEY PATTERN (your system)

### WRITE path

```id="write"
incident_reports → processing → incidents
```

### READ path

```id="read"
incidents / summaries / feeds
```

---

# CRITICAL RULES (do not break)

1. Never expose:

```id="no-expose"
incident_cluster_*
*_snapshots
*_metrics
processing tables
```

2. Always read from:

```id="read-optimized"
incident_map_feed
vehicle_*_summaries
corridor_*_summaries
```

3. Always write to:

```id="write-raw"
incident_reports
ride_feedback
```

---

# FINAL STRUCTURE

```id="final"
tibs-api
  ├── reports (write)
  ├── incidents (read)
  ├── vehicles (lookup)
  ├── corridors
  ├── routes
  ├── saccos
  ├── feedback
  ├── surveyor
  ├── learning
  └── admin
```


