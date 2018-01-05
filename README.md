# autoschedule

An intelligent scheduling system for solving simple room scheduling problems.

## Setup

First, make sure you have a recent version of Python 3 and virtualenv on your
system. Create a virtual environment to isolate all the required packages.

```sh
virtualenv -p python3 env
source env/bin/activate
pip install -r requirements.txt
```

Then, open Jupyter Notebook and open the iPython notebooks.

```sh
jupyter notebook
```

## Starting a new semester

First, branch off of master.

```sh
git checkout -b {SEMESTER}
```

### Room scheduling

The first task for scheduling rooms is to acquire rooms. Book all the available
slots, then update the `rooms.yml` file with the room availibility.

We'll also need to collect fresh preferences: create a Google Form with
multiple-choice checkboxes where each row represents the day and each column
represents a possible start time. Download the data into a file named
`preferences.csv`.

The rest of the work is done in the room scheduling notebook.

### Student scheduling

Once rooms have been assigned, the room scheduling script should output a CSV
file containing all the assignments, `room_schedule.csv`, which will be used
by the section scheduling notebook.

Collect student preferences for sections by taking the room schedule and
generating control codes for each section. Students will mark their preferred
sections by copy-pasting control codes into a Google Form. The system will then
solve for the optimal assignment of students to sections.
