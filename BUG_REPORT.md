# Bug Fix Report

## Project

Conference Room Booking API

## Summary

During the preliminary hackathon, we identified and fixed 10 bugs across the application. The fixes improved concurrency safety, booking validation, pagination, room availability, reporting, and overall reliability.

## Bugs Fixed

| No. | File                          | Issue Fixed                                                   |
| --- | ----------------------------- | ------------------------------------------------------------- |
| 1   | app/timeutils.py              | Fixed date and time handling issue                            |
| 2   | app/services/notifications.py | Fixed notification deadlock issue                             |
| 3   | app/services/ratelimit.py     | Fixed race condition in the rate limiter                      |
| 4   | app/services/reference.py     | Fixed race condition while generating booking reference codes |
| 5   | app/services/stats.py         | Fixed concurrent room statistics update issue                 |
| 6   | app/routers/bookings.py       | Fixed booking pagination offset and dynamic limit             |
| 7   | app/routers/bookings.py       | Fixed minimum and maximum booking-duration validation         |
| 8   | app/routers/bookings.py       | Fixed room booking conflict boundary condition                |
| 9   | app/routers/bookings.py       | Fixed quota-window boundary condition                         |
| 10  | app/routers/rooms.py          | Fixed room availability boundary issue                        |

## Validation

The application was tested after applying all fixes using:

```bash
pytest -q
```

Final test result:

```text
1 passed
```

The Git working tree was also verified to be clean after merging all fixes.
