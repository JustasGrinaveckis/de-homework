<h1 style="text-align: center;">Data Engineer homework task</h1> 

In this task you will be parsing metadata from two types of [DBT](https://www.getdbt.com/) models metadata: [freshness](https://docs.getdbt.com/reference/resource-properties/freshness#definition) and [tests](https://docs.getdbt.com/docs/build/tests#overview)

End result is two tables in [BigQuery](https://cloud.google.com/bigquery) for each type of metadata.
Schema for these tables is called <code>de_hw_NAME_SURNAME</code> </br>
Project name - **kilo-dw** </br>
Project number - **152882472640** </br>

<h2 style="text-align: center;">Freshness</h2> 

Path to files folder <code>gs://kilo_de_hw_files/freshness/</code>
</br>
Name of table in BigQuery - <code>freshness_results</code> </br>
Full table path would be *kilo-dw.de_hw_NAME_SURNAME.freshness_results* </br>
</br>
Columns:
- id
- project_name
- schema_name
- table_name
- latest_loaded_at
- queried_at
- time_since_last_row_arrived_in_s
- status
- filter_field
- filter_type
- filter_value
- warn_after_period
- warn_after_value
- error_after_period
- error_after_value
- bytes_processed
- bytes_billed
- job_location
- job_project_id
- slot_ms
- price (this one is calculated using *bytes_billed* column)
- started_at
- completed_at

Data types for each column can be set based on your own expertise. </br>

</br>

<h2 style="text-align: center;">Test</h2> 

Path to files folder <code>gs://kilo_de_hw_files/test/</code> </br>
Name of table in BigQuery - <code>test_results</code> </br>
Full table path would be *kilo-dw.de_hw_NAME_SURNAME.test_results* </br>
Columns:
- id
- table_name
- name
- status
- execution_time_in_s
- message
- failed_rows
- bytes_processed
- bytes_billed
- job_location
- job_project_id
- slot_ms
- price (this one is calculated using *bytes_billed* column)
- started_at
- completed_at

Data types for each column can be set based on your own expertise. </br>
Both tables have to have partitioning and clustering columns </br>
</br>
Reading from Google Cloud Storage and loading to BigQuery can be done after authentication. This is done using email that you provided before receiving task. </br>
It's strongly recommended to use Python programming language for task completion as well as [Python SDK](https://cloud.google.com/python/docs/getting-started) when communicating with GCP. </br>
Setting up environment (venv or installing in base env) is solely upon one's wants and needs. It won't be evaluated.
</br>
End result is a link to private github repo with written code. </br>
Resources:
- [gcloud CLI](https://cloud.google.com/sdk/docs/install-sdk)
- <code>gcloud auth application-default login</code> - to login with ADC
