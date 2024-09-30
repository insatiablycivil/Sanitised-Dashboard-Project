# Sanitised-Dashboard-Project

## Background
1 Year project. Looking at millions of rows of data, 1000s of files, 100s of GBs.
Goal was to develop of pipeline that can make sense of the raw data by giving it a structure, that can then make it interrogable.
The parsed data was then to be the foundation of further data analytics for condition monitoring purposes.

![alt text](/Dashboard_General_SetUp.png "Flowchart of Overall Process")

## Scope
This project was initially scoped to be using Jupyter Notebook interface relying on IPyWidget-based GUI for the dashboard and MySQL for the backend. 
Midway through, it was pivoted to having PowerBI be the dashboard and MS SQL be the backend. The codebase was in Python.

I managed to create a pipeline for raw data to the dashboard. This included:
  * Custom Parser of the raw data in python
  * Custom Interpretter of parsed data with several error-correction algorithms to further structure the data in Python
  * Custom database design to allow for efficient storage and retreival of a high volume of data.
  * Custom PowerBI Dashboard fed from said DB, that allowed for various metrics to be viewed.

![alt text](/Dashboard_Stages.png "List of Developed Functionality")

## Value-Added
The "novelty" / my focus, was on the ability to have full backwards traceability from a given metric to the raw data.
This was challenging because: 
  * There were many-to-many relationships between metrics and raw data.
  * The raw data at times had errors that needed corrections.
  * The volume of data exceeded the baseline capabilities of PowerBI
  * Careful database design was required to allow for the presented functionality making using of hierarchical relationships to dynamically import only what was needed for a given request.

![alt text](/Dashboard_Database_SetUp.png "View of Designed Database Structure")

## Summary
The end product was incomplete, however. There were too many time-sync issues with the raw data for me to consistantly algorithmically coordinate into a cohesive output.
I documented as many sub-types of these issues as I found, and began various prototypes tackling each of them before my time ended (1 year project). 
The presented demo at the end of the project was able to process end-to-end a pre-selected 6-month span of the data.
Unfortunately, the only "analytic" I managed to implement beyond the pipeline, was one to detect comm. failures. 
My custom parser was sufficiently reliable that when it failed, it was due to corrupted data, excess occurances indicated comm. failures.

![alt text](/Dashboard_Anomaly.png "Demonstration of Anomaly Detection")
Please note, I do not feel comfortable to share the overall dashboard. 
It of course contained a lot more information and context, with ability to drilldown and view different aspects across multiple tabs/pages!
Another aspect not visible is the extensive knowledge elicitation from the SMEs via weekly meetings that I chaired to facilitate the development of the project. 
The raw data did not have a simple, or even singular, structure / lexicon that could be easily interpretted by a layperson. 
Instead, different periods of time and locations would have different structures.
Though, unfortunately, once again, I cannot show the code or the data to demonstrate this aspect.
