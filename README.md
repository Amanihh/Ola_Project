# 🚕 OLA Ride Booking Analytics — SQL & Power BI

A data analyst case study on one month of OLA ride-booking data for Bengaluru city — built to simulate a real analyst workflow: raw data → SQL analysis → Power BI dashboard → business insight.

The project answers 10 core business questions (via SQL views) and visualizes booking volume, cancellations, ratings, and revenue across a 5-page interactive dashboard.

---

## 📊 Dataset

| | |
|---|---|
| **Rows** | 1,00,000 bookings |
| **Period** | 1 month (July 2024) |
| **City** | Bengaluru |
| **File** | `Bookings.csv` |

**Columns:**

`Date`, `Time`, `Booking_ID`, `Booking_Status`, `Customer_ID`, `Vehicle_Type`, `Pickup_Location`, `Drop_Location`, `V_TAT`, `C_TAT`, `Canceled_Rides_by_Customer`, `Canceled_Rides_by_Driver`, `Incomplete_Rides`, `Incomplete_Rides_Reason`, `Booking_Value`, `Payment_Method`, `Ride_Distance`, `Driver_Ratings`, `Customer_Rating`

**Simulated data constraints:**
- Successful bookings: ~62%
- Cancelled by customer: ≤ 7%
- Cancelled by driver: ≤ 18%
- Incomplete rides: ≤ 6%
- Higher order volume on weekends & match days
- Higher order values on weekends

---

## 🛠 Tech Stack

- **MySQL** — data modeling, views, aggregation
- **Power BI** — interactive dashboarding
- **CSV** — source data (`Bookings.csv`)

---

## 🧮 SQL Analysis

`Ola_Project.sql` creates 10 reusable views, each answering a specific business question:

| # | Business Question | View |
|---|---|---|
| 1 | All successful bookings | `successful_booking` |
| 2 | Average ride distance per vehicle type | `ride_distance_for_each_vehicle` |
| 3 | Total rides cancelled by customers | `canceled_by_customer` |
| 4 | Top 5 customers by ride volume | `top_5_customer` |
| 5 | Driver cancellations — personal/car issues | `ride_cancled_by_driver_p_c_issues` |
| 6 | Max/min driver ratings — Prime Sedan | `max_min_driver_rating_sedan` |
| 7 | All UPI-paid rides | `upi_payment` |
| 8 | Average customer rating per vehicle type | `avg_customer_rating_per_vehicle` |
| 9 | Total booking value of successful rides | `successful_rides` |
| 10 | Incomplete rides with reasons | `incomplete_rides_with_reason` |

---

## 📈 Power BI Dashboard

A 5-page interactive report (`Ola_Project.pbix`):

1. **Overall** — total bookings, booking value, status breakdown, ride volume over time
2. **Vehicle Type** — booking value, success value, and distance travelled per vehicle
3. **Revenue** — revenue by payment method, top 5 customers, ride distance distribution per day
4. **Cancellation** — cancellation reasons split by driver vs. customer
5. **Ratings** — driver and customer ratings by vehicle type

### Key Numbers
- **1,03,024** total bookings, **₹35M+** total booking value
- **62.09%** success rate · 17.89% driver-cancelled · 10.19% customer-cancelled · 9.83% driver not found
- Top driver-cancellation reason: **Personal & car related issue (35.49%)**
- Top customer-cancellation reason: **Driver not moving towards pickup (30.24%)**
- **Cash** and **UPI** are the dominant payment methods (~₹19M and ~₹15M)

---

## 🚀 Setup

1. **Database**
   ```bash
   mysql -u root -p < Ola_Project.sql
   ```
   Load `Bookings.csv` into a `bookings` table in the `OLA_PROJECT` database, matching the column names listed above, then run the view-creation queries.

2. **Dashboard**
   - Open `Ola_Project.pbix` in Power BI Desktop, **or**
   - Open `Ola_Project.pbit` (template) and point it to your own copy of `Bookings.csv`
   - Refresh data to load

---

## 📁 Files

| File | Description |
|---|---|
| `Bookings.csv` | Raw source data |
| `Ola_Project.sql` | Database + 10 analysis views |
| `Ola_Project.pbix` | Power BI dashboard (with data) |
| `Ola_Project.pbit` | Power BI template (structure only) |

---

## 🖼 Screenshots

**Overall**
![Overall](https://github.com/Parvin24Kumar/Ola_Project/blob/main/ScreenShot%20-%20Overall.png?raw=true)

**Vehicle Type**
![Vehicle Type](https://github.com/Parvin24Kumar/Ola_Project/blob/main/ScreenShot%20-%20Vehicle%20Type.png?raw=true)

**Revenue**
![Revenue](https://github.com/Parvin24Kumar/Ola_Project/blob/main/ScreenShot%20-%20Revenue.png?raw=true)

**Cancellation**
![Cancellation](https://github.com/Parvin24Kumar/Ola_Project/blob/main/ScreenShot%20-%20Cancellation.png?raw=true)

**Ratings**
![Ratings](https://github.com/Parvin24Kumar/Ola_Project/blob/main/ScreenShot%20-%20Ratings.png?raw=true)
