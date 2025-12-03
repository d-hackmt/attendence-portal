This is the beginning of my project lets goo

to make virtual environment we used uv

```
uv init
```

```
uv venv venv
```

```text
Attendence/
│
├── admin.py              → Admin dashboard logic
├── analytics.py          → Attendance analytics
├── clients.py            → Supabase client builder
├── config.py             → Environment/config loader
├── logger.py             → Central logging system
├── student.py            → Student attendance UI + logic
├── supabase_client.py    → (deprecated now, merged into clients)
├── utils.py              → Shared helpers (dates, etc.)
│
├── admin_main.py         → Streamlit entry for admin
├── student_main.py       → Streamlit entry for student
│
├── logs/
│   └── app.log           → Combined logs
│
├── records/              → CSV exports for admin analytics
│
├── pyproject.toml        → Project dependencies
├── requirements.txt      → For pip installs
├── versions.py           → Prints package versions
```

### How real logs look like

```text

2025-12-01 20:15:32,891 | INFO | Attendence.student | student.py:45 | show_student_panel() | Fetching open classes from Supabase…

2025-12-01 20:15:33,104 | DEBUG | Attendence.clients | clients.py:22 | create_supabase_client() | Supabase client initialized successfully.

2025-12-01 20:15:33,982 | ERROR | Attendence.student | student.py:78 | show_student_panel() | Failed to fetch roll map

2025-12-01 20:15:33,982 | ERROR | Attendence.student | student.py:78 | show_student_panel() | Traceback (most recent call last):

2025-12-01 20:15:33,982 | ERROR | Attendence.student | student.py:78 | show_student_panel() |   File "Attendence/student.py", line 65, in show_student_panel

2025-12-01 20:15:33,982 | ERROR | Attendence.student | student.py:78 | show_student_panel() |     roll_map_response = supabase.table("roll_map")...

2025-12-01 20:15:33,982 | ERROR | Attendence.student | student.py:78 | show_student_panel() | postgrest.exceptions.APIError: invalid input syntax for integer: ""

2025-12-01 20:15:34,120 | WARNING | Attendence.admin | admin.py:102 | toggle_classroom() | Classroom '8 C' was already open.

2025-12-01 20:15:34,982 | INFO | Attendence.admin | admin.py:150 | download_attendance_report() | Report generated: attendance_matrix_8C_20251201.csv


```