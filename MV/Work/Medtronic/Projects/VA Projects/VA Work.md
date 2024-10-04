#### Meeting on 2024-07-30 with [[Work/Medtronic/People/David|David]]
- What metrics needed?
- Where to get them?
- How to present?

## Scaffolding
- Reporting Period
	- Will need to define "Month" as Calendar Month
	- "Active" means in the member table where there are no enrollment (type 1) and no disenrollment (type 2) during that month
	- Disenrollment is type 2 during the Reporting Period with timestamp
	- Enrollment is with type 1, during Reporting peroid (possible re-enrollment or care coordinator change, put it in notes)
- Logic Order
	- Active if Enrolled
	- Enrollment if EnrollmentDate in month period 
	- Disenrollment if DisenrollmentDate in month period

## Requirements

#### Part 1: Active
#### Part 2 : Enrollments
#### Part 3: Disenrollments

All should be mutually exclusive, meaning each veteran appears in only one

- Reference Columns
	- DeviceType.DeviceName
		- Interview, Commander Flex, etc
	- DiseaseProgram.ProgramName, DiseaseProgram.ProgramDescription
		- Diabetes, Asthma, etc
	- MemberFacility.[MemberId, FacilityId]
		- will get the memberId and facilityid to use in 
	- RegionFacility.[RegionID, FacilityID]
		- will get the region associated with a facilityId
	- Region.[RegionID,RegionName,RegionDescription]
		- Shows VISNs for each region

- Columns
	- ICN
		- Patient Member id?
	- VISN
		- VA Location
		- MemberId -> MemberFAcility -> RegionFacility -> Region
	- Site (managed group)
		- MemberDetail.ManagedGroupId
		- MemberId -> ManagedGroupId
	- Platform
		- DeviceType for DeviceName
		- DeviceRegistration for DeviceRegistrationId
		- MemberId -> DeviceRegistration.DeviceRegistrationId, UnitID
	- Primary DMP
		- Diabetes platform?
		- Needs DiseaseProgram (for program name), 
	- Comorbid DMP(s)
		- FlexComorbidity.[Id, Name, Abbrev, DiseaseProgramId]
	- Media version
		- DeviceRegistration.DeviceRegistrationID, DeviceRegistration.MemberID, DeviceRegistration.MediaVersion
	- Firmware version
		- DeviceRegistration.UnitVersion ??
		- Just a guess
	- Care Coordinator
		- Relationship.Profession (shows care coordinator)
		- Relationship.RelationshipId
	- Category of Care
	- Days on Service
		- ???
		- Will do Current Date - Enrollment Date in days
	- Enrollment Date
		- MembersEnrolledInDateRange sproc
		- MemberEnrollment.MemberID, MemberEnrollment.ActionDate where ActionID = 1 for date range
	- Disenrollment Date
		- MemberEnrollment where not 1 for date range

## Useful Tables
- Relationship
	- Shows Care Coordinators, FirstName, LastName, Profession(care coordinator), email, facilityid (location), npi, active (1 or 0)
- MemberFacility
	- Facilities by MemberID
- MemberEnrollment
	- Shows Enrolled or Disenrolled (anything but 1 is disenrolled)
- MemberDetail
	- Shows MemberId, ManagedGroup

## Useful Sprocs
- FacilityByMemberId
	- 
- sel_MembersEnrolledInDateRange
	- members enrolled by date range
