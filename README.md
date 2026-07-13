```mermaid
graph LR
    classDef default fill:#f9f9f9,stroke:#333,stroke-width:1px;
    classDef layer1 fill:#99ccff,stroke:#333,stroke-width:1.5px,font-weight:bold;
    classDef layer2 fill:#ccffcc,stroke:#333,stroke-width:1px,font-weight:bold;
    classDef layer3 fill:#fff,stroke:#666,stroke-width:1px,stroke-dasharray: 2 2,font-size:11px;

    %% Root
    am[8. Admin & Monitoring]:::layer1

    %% NỬA BÊN TRÁI
    am_bs[Background Strategy]:::layer2 --- am
    am_bs1[Background Worker]:::layer3 --- am_bs
    am_bs2[Scheduler]:::layer3 --- am_bs
    am_bs3[Auto Vacuum]:::layer3 --- am_bs
    am_bs4[Statistics Collection]:::layer3 --- am_bs
    am_bs5[Backup Scheduler]:::layer3 --- am_bs

    am_ml[Monitoring & Logging]:::layer2 --- am
    am_ml1[Performance Metrics Collector]:::layer3 --- am_ml
    am_ml2[Slow Query Profiler]:::layer3 --- am_ml
    am_ml3[System Error Log Writer]:::layer3 --- am_ml

    %% NỬA BÊN PHẢI
    am --- am_cm[Configuration]:::layer2
    am_cm --- am_cm1[Config Parameters Registry]:::layer3
    am_cm --- am_cm2[Dynamic Parameter Reloader]:::layer3

    am --- am_ie[Import & Export Utilities]:::layer2
    am_ie --- am_ie1[Bulk COPY Loader]:::layer3
    am_ie --- am_ie2[Binary Importer]:::layer3
    am_ie --- am_ie3[CSV Importer]:::layer3
    am_ie --- am_ie4[Logical Dump Utility]:::layer3
    am_ie --- am_ie5[Restore Utility]:::layer3
    am_ie --- am_ie6[Data Export Manager]:::layer3
```
