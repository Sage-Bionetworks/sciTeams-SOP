## AMP-AD (to be applied to other consortia) data quality annotation
**Purpose**: Improved data validation tools lead to use cases where data quality issues were not identified at the time of upload and public data release. The data quality annotation is meant to flag data users of these issues. The objective is to (1) alert users of the problematic file and (2) provide users a direct link to release notes for comprehensive QC details.

**Definition**:

data quality annotation - `failedQC = TRUE`

release notes -  supporting documentation for data sets made public during a release, accessible via `entityId`

**Procedure**: 
When a quality issue is identified, the set of files are annotated with `failedQC = TRUE` and `releaseNotes = entityId`, where entityId is the synId of the relevant data release notes.  
`forceVersion = FALSE` is an argument in `synStore()` to assign `failedQC = TRUE` to the existing file version. Data release notes are tracked in syn2580853 for AMP-AD. The `entityId` annotation is expected to link to documentation containing differences between the two freezes and QC criteria.

Example `synapser`:
```
synapse_fv <- synTableQuery("Select * from syn18518533")
fv <- readr::read_csv(synapse_fv$filepath)
fv$failedQC[fv$id %in% c("syn18424903")] <- TRUE
x <- synStore(Table(synapse_fv$tableId, fv), forceVersion = FALSE)
```

The new data freeze will only include files with the annotation `failedQC = NA`. Therefore, the data freeze may be a subset of the previous data freeze. 
