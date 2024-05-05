# AWS Disaster Recovery and Management Workflow

This is a project made by me and my teammates to handle a disaster for a company.

This project works in the following steps - 
- **Phase 1 -** We built the basic infrasturcture which the client will have. This includes the instances, applications in those instances and the files in the EBS file system.
- **Phase 2 -** We then write a function which would create regular AMI backups of these instances on a regular basis, which is normally a daily basis. This duration can be customized. We store these in S3.
- **Phase 3 -** We now implement the disaster recovery. We write the Lambda function to duplicate the insfrastructure in the backup region if a disaster happens in the main region where the servers are present. All the data from the backups is recovered here and the users can use the application without knowing there was a disaster.
- **Phase 4 -** We fix the disaster, and once it is handled we switch back to the main region's server in the same way.

This is the current status of the project we have made so far. This project can be significantly upgraded. 

### Future Scope
- [ ] Add RDS Backup and Sync support
- [ ] Implement Route 53 for automatic DNS resolution to the backup region's IPs
- [ ] Automatic removal of old backups and versionings
- [ ] Refactor the Lambda function

