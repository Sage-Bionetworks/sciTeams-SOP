## Criteria to Remove Data from Synapse

**Purpose**: To establish Sage standards for data redaction and provide user-facing documentation. Data will typically be updated via an incremental file version or quality control annotation. In the case of a governance breach, data will be fully redacted.

**Definition**:

redaction - Data is permanently removed from Synapse. Sage Bionetworks will not recover redacted Synapse data. This includes all versions of the file and any associated metadata entries. 

governance breach - Data has been released that shouldn’t have been such as PHI data or data that has not been consented for sharing. Samples are removed from a consortia at the request of its governing body (e.g. NIMH).

**Procedure**: Data stored in Synapse will be redacted only in the case of a governance breach. This breach must be documented in the Governance Violations or Incidents Google sheet (pending Jira) (insert link). In the case of a replacement file, all previous versions of the file must be deleted. For managing a scenario where a data contributor flags existing Synapse-stored data as being of questionable quality, reference the [data quality annotation SOP](https://github.com/Sage-Bionetworks/sciTeams-SOP/blob/master/docs/data_quality_annotation.md).
