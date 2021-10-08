### United States COVID-19 Cases and Deaths by State over Time

#### Description

This aggregate dataset is structured to include daily numbers of confirmed and probable case and deaths reported to CDC by states over time.

#### Usage

`US_deaths_cases`

#### Format

A data frame with 37,380 rows and 15 variables:

- `submission_date`: Date of counts
- `state`: Jurisdiction
- `tot_cases`: Total number of cases
- `conf_cases` : Total confirmed cases
- `prob_cases` : Total probable cases
- `new_case` : Number of new cases
- `pnew_case` : Number of new probable cases
- `tot_death` : Total number of deaths
- `conf_death` : Total number of confirmed deaths
- `prob_death` : Total number of probable deaths
- `new_death` : Number of new deaths
- `pnew_death` : Number of new probable deaths
- `created_at` : 	Date and time record was created
- `consent_cases` : If Agree, then confirmed and probable cases are included. If Not Agree, then only total cases are included.
- `consent_deaths` : If Agree, then confirmed and probable deaths are included. If Not Agree, then only total deaths are included.

#### Source

See https://data.cdc.gov/Case-Surveillance/United-States-COVID-19-Cases-and-Deaths-by-State-o/9mfq-cb36. The data was drawn from the website on October 6th, 2021. 

### COVID-19 Vaccinations in the United States Jurisdiction

#### Description

Overall US COVID-19 Vaccine deliveries and administration data at national and jurisdiction level. Data represents all vaccine partners including jurisdictional partner clinics, retail pharmacies, long-term care facilities, dialysis centers, Federal Emergency Management Agency and Health Resources and Services Administration partner sites, and federal entity facilities.

#### Usage

`US_vaccinations`

#### Format

A data frame with 19,208 rows and 81 variables:

- `Date` : Date
- `MMWR_week` : Morbidity and Mortality Weekly Report 
- `Location` : State/Territory/Federal Entity
- `Distributed` : Total number of distributed doses
- `Distributed_Janssen` : Total number of J&J/Janssen doses delivered
- `Distributed_Moderna` : Total number of Moderna doses delivered
- `Distributed_Pfizer` : Total number of Pfizer-BioNTech doses delivered
- `Distributed_Unk_Manuf` : Total number of doses from unknown manufacturer delivered
- `Dist_Per_100K` : Delivered doses per 100,000 census population
- `Distributed_Per_100k_12Plus` : Total number of delivered doses per 100,000 12+ population
- `Distributed_Per_100k_18Plus` : Total number of delivered doses per 100,000 18+ population
- `Distributed_Per_100k_65Plus` : Total number of delivered doses per 100,000 65+ population
- `Administered` : Total number of administered vaccines based on state where administered
- `Administered_12Plus` : Total number of doses administered to people 12+ based on the jurisdiction where recipient lives
- `Administered_18Plus` : Total number of doses administered to people 18+ based on the jurisdiction where recipient lives
- `Administered_65Plus` : Total number of doses administered to people 65+ based on the jurisdiction where recipient lives
- `Administered_Janssen` : Total number of J&J/Janssen doses administered
- `Administered_Moderna` : Total number of Moderna doses administered
- `Administered_Pfizer` : Total number of Pfizer-BioNTech doses administered
- `Administered_Unk_Manuf` : Total number of doses from unknown manufacturer administered
- `Administered_Fed_LTC` : Total number of doses administed to long-term care facilities
- `Administered_Fed_LTC_Residents` : Total number of doses administed to long-term care facility residents
- `Administered_Fed_LTC_Staff` : Total number of doses administed to long-term care facility staff
- `Administered_Fed_LTC_Unk` : Total number of doses administed to other people in long-term care facility
- `Administered_Fed_LTC_Dose1` : Total number of people with at least one dose of any vaccine in long-term care facilities
- `Administered_Fed_LTC_Dose1_Residents` : Total number of residents with at least one dose of any vaccine in long-term care facilities
- `Administered_Fed_LTC_Dose1_Staff` : Total number of staff with at least one dose of any vaccine in long-term care facilities
- `Administered_Fed_LTC_Dose1_Unk` : Total number of other people with at least one dose of any vaccine in long-term care facilities
- `Admin_Per_100K` : Total number of doses administered per 100,000 census population based on the jurisdiction where recipient lives
- `Admin_Per_100K_12Plus` : Total number of doses administered to people 18+ per 100,000 12+ populations
- `Admin_Per_100K_18Plus` : Total number of doses administered to people 18+ per 100,000 18+ populations
- `Admin_Per_100K_65Plus` : Total number of doses administered to people 65+ per 100,000 65+ populations
- `Recip_Administered` : Total number of administered vaccines based on the jurisdiction of residence
- `Administered_Dose1_Recip` : Total number of people with at least one dose based on the jurisdiction where recipient lives
- `Administered_Dose1_Pop_Pct` : Percent of population with at lease one dose based on the jurisdiction where recipient lives
- `Administered_Dose1_Recip_12Plus` : Total number of people 12+ with at least one dose based on the jurisdiction where recipient lives
- `Administered_Dose1_Recip_12PlusPop_Pct` : Percent of 12+ population with at least one dose based on the jurisdiction where recipient lives
- `Administered_Dose1_Recip_18Plus` : Total number of people 18+ with at least one dose based on the jurisdiction where recipient lives
- `Administered_Dose1_Recip_18PlusPop_Pct` : Percent of 18+ population with at least one dose based on the jurisdiction where recipient lives
- `Administered_Dose1_Recip_65Plus` : Total number of people 65+ with at least one dose based on the jurisdiction where recipient lives
- `Administered_Dose1_Recip_65PlusPop_Pct` : Percent of 65+ population with at lease one dose based on the jurisdiction where recipient lives
- `Series_Complete_Yes` : Total number of people who are fully vaccinated (have second dose of a two-dose vaccine or one dose of a single-dose vaccine) based on the jurisdiction where recipient lives
- `Series_Complete_Pop_Pct` : Percent of people who are fully vaccinated (have second dose of a two-dose vaccine or one dose of a single-dose vaccine) based on the jurisdiction where recipient lives
- `Series_Complete_12Plus` : Total number of people 12+ who are fully vaccinated (have second dose of a two-dose vaccine or one dose of a single-dose vaccine) based on the jurisdiction where recipient lives
- `Series_Complete_12PlusPop_Pct` : Percent of people 12+ who are fully vaccinated (have second dose of a two-dose vaccine or one dose of a single-dose vaccine) based on the jurisdiction where recipient lives
- `Series_Complete_18Plus` : Total number of people 18+ who are fully vaccinated (have second dose of a two-dose vaccine or one dose of a single-dose vaccine) based on the jurisdiction where recipient lives
- `Series_Complete_18PlusPop_Pct` : Percent of people 18+ who are fully vaccinated (have second dose of a two-dose vaccine or one dose of a single-dose vaccine) based on the jurisdiction where recipient lives
- `Series_Complete_65Plus` : Total number of people 65+ who are fully vaccinated (have second dose of a two-dose vaccine or one dose of a single-dose vaccine) based on the jurisdiction where recipient lives
- `Series_Complete_65PlusPop_Pct` : Percent of people 65+ who are fully vaccinated (have second dose of a two-dose vaccine or one dose of a single-dose vaccine) based on the jurisdiction where recipient lives
- `Series_Complete_Janssen` : Total number of people who are fully vaccinated with the J&J/Janssen vaccine based on the jurisdiction where recipient lives
- `Series_Complete_Moderna` : Total number of people who are fully vaccinated with the Moderna vaccine based on the jurisdiction where recipient lives
- `Series_Complete_Pfizer` : Total number of people who are fully vaccinated with the Pfizer vaccine based on the jurisdiction where recipient lives
- `Series_Complete_Unk_Manuf` : Total number of people who are fully vaccinated with two doses from an uknown two-dose vaccine manufacturer based on the jurisdiction where recipient lives
- `Series_Complete_Janssen_12Plus` : Total number of people 12+ who are fully vaccinated with the J&J/Janssen vaccine based on the jurisdiction where recipient lives
- `Series_Complete_Moderna_12Plus` : Total number of people 12+ who are fully vaccinated with the Moderna vaccine based on the jurisdiction where recipient lives
- `Series_Complete_Pfizer_12Plus` : Total number of people 12+ who are fully vaccinated with the Pfizer vaccine based on the jurisdiction where recipient lives
- `Series_Complete_Unk_Manuf_12Plus` : Total number of people 12+ who are fully vaccinated with two doses from an uknown two-dose vaccine manufacturer based on the jurisdiction where recipient lives
- `Series_Complete_Janssen_18Plus` : Total number of people 18+ who are fully vaccinated with the J&J/Janssen vaccine based on the jurisdiction where recipient lives
- `Series_Complete_Moderna_18Plus` : Total number of people 18+ who are fully vaccinated with the Moderna vaccine based on the jurisdiction where recipient lives
- `Series_Complete_Pfizer_18Plus` : Total number of people 18+ who are fully vaccinated with the Pfizer vaccine based on the jurisdiction where recipient lives
- `Series_Complete_Unk_Manuf_18Plus` : Total number of people 18+ who are fully vaccinated with two doses from an uknown two-dose vaccine manufacturer based on the jurisdiction where recipient lives
- `Series_Complete_Janssen_65Plus` : Total number of people 65+ who are fully vaccinated with the J&J/Janssen vaccine based on the jurisdiction where recipient lives
- `Series_Complete_Moderna_65Plus` : Total number of people 65+ who are fully vaccinated with the Moderna vaccine based on the jurisdiction where recipient lives
- `Series_Complete_Pfizer_65Plus` : Total number of people 65+ who are fully vaccinated with the Pfizer vaccine based on the jurisdiction where recipient lives
- `Series_Complete_Unk_Manuf_65Plus` : Total number of people 65+ who are fully vaccinated with two doses from an uknown two-dose vaccine manufacturer based on the jurisdiction where recipient lives
- `Series_Complete_FedLTC` : Total number of doses administed to long-term care facilities
- `Series_Complete_FedLTC_Residents` : Total number of doses administed to long-term care facility residents
- `Series_Complete_FedLTC_Staff` : Total number of doses administed to long-term care facility staff
- `Series_Complete_FedLTC_Unknown` : Total number of doses administed to other people in long-term care facility
- `Additional_Doses` : Total number of people who are fully vaccinated and have received a booster (or additional) dose.
- `Additional_Doses_Vax_Pct` : Percent of people who are fully vaccinated and have received a booster (or additional) dose.
- `Additional_Doses_18Plus` : Total number of people 18+ that are fully vaccinated and have received a booster (or additional) dose.
- `Additional_Doses_18Plus_Vax_Pct` : 	
Percent of people 18+ who are fully vaccinated and have received a booster (or additional) dose.
- `Additional_Doses_50Plus` : Total number of people 50+ that are fully vaccinated and have received a booster (or additional) dose.
- `Additional_Doses_50Plus_Vax_Pct` : 	
Percent of people 50+ who are fully vaccinated and have received a booster (or additiuonal) dose.
- `Additional_Doses_65Plus` : Total number of people 65+ that are fully vacinated and have received a booster (or additional) dose.
- `Additional_Doses_65Plus_Vax_Pct` : Percent of people 65+ who are fully vaccinated and have received a booster (or additional) dose.
- `Additional_Doses_Moderna` : Total number of fully vaccinated people who have received a Moderna booster (or additional) dose.
- `Additional_Doses_Pfizer` : Total number of fully vaccinated people who have received a Pfizer booster (or additional) dose.
- `Additional_Doses_Janssen` : Total number of fully vaccinated people who have received a Janssen booster (or additional) dose.
- `Additional_Doses_Unk_Manuf` : Total number of fully vaccinated people who have received an other or unknown booster (or additional) dose.

#### Source

See https://data.cdc.gov/Vaccinations/COVID-19-Vaccinations-in-the-United-States-Jurisdi/unsk-b7fc. The data was drawn from the website on October 6th, 2021.
