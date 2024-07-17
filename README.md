# MedicalOne Database Project

This project contains the SQL scripts and schema design for the MedicalOne database system, which manages patient information, bookings, vaccinations, appointments, medical centers, doctors, and managerial histories. The database schema is designed to handle various aspects of a medical center's operations, including patient registrations, doctor assignments, appointment bookings, and vaccination records.

## Project Structure

### Database Schema

The database schema consists of the following tables:

- **PATIENT**: Stores patient information.
  - `PAT_ID` (Primary Key)
  - `PAT_NAME`
  - `PAT_ADD`
  - `PAT_NUM`

- **BOOKING**: Stores booking details.
  - `BOOKING_ID` (Primary Key)
  - `PAT_ID` (Foreign Key)
  - `DOC_ID` (Foreign Key)
  - `BOOKING_DATE`

- **VACCINATION**: Stores vaccination records.
  - `BOOKING_ID` (Primary Key)
  - `VAC_TYPE` (with a constraint to ensure valid values: 'Covid', 'Polio', 'Measles')
  - `VAC_DOSE`
  - `MCARE_NUM`

- **APPOINTMENT**: Stores appointment details.
  - `BOOKING_ID` (Primary Key)
  - `PAT_TYPE` (with a constraint to ensure valid values: 'Checkup', 'Treatment')

- **CENTRE**: Stores medical center information.
  - `C_ID` (Primary Key)
  - `C_NAME`
  - `C_ADD`
  - `C_NUM`
  - `C_FAX`
  - `C_PRC_MGR`

- **TIMING**: Stores opening and closing hours for medical centers.
  - `DAYS` (Primary Key)
  - `C_ID` (Foreign Key)
  - `OPENING_HOUR`
  - `CLOSING_HOUR`

- **DOCTOR**: Stores doctor information.
  - `DOC_ID` (Primary Key)
  - `C_ID` (Foreign Key)
  - `DOC_NAME`
  - `DOC_NUM`
  - `DOC_SOURCE`

- **MANAGER_HISTORY**: Stores the history of center managers.
  - `C_ID` (Primary Key)
  - `DATE_ASSIGN`
  - `EMP_NUM` (added later via an ALTER TABLE statement)

### SQL Scripts

The project includes SQL scripts for:

- Creating tables
- Dropping existing tables if they exist
- Inserting sample data into the tables
- Updating and querying the data
- Creating views to present specific subsets of the data

### Sample Data

Sample data is provided for each table to illustrate the structure and relationships within the database. The sample data includes:

- Patient records with IDs, names, addresses, and contact numbers.
- Medical centers with IDs, names, addresses, contact numbers, fax numbers, and managers.
- Doctors assigned to specific centers.
- Bookings for appointments and vaccinations.
- Vaccination records with types and doses.
- Timings for center operations.
- Managerial history for center managers.

### Views

The project includes a view named `Third_dose_vaccine_centres`, which provides a list of centers that have administered three or more doses of vaccines.

### Queries

Sample queries are provided to demonstrate how to retrieve and update data within the database, including:

- Retrieving all patients, centers, doctors, bookings, vaccinations, timings, and manager history records.
- Updating booking dates.
- Selecting specific managerial details based on operational days.

## How to Use

1. Clone the repository to your local machine.
2. Execute the SQL scripts in your SQL environment to create the database schema.
3. Insert the sample data to populate the tables.
4. Run the provided queries to interact with and manage the data.

## Contributions

Contributions to this project are welcome. If you have suggestions for improvements or additional features, please submit a pull request or open an issue.

## License

This project is licensed under the MIT License.
