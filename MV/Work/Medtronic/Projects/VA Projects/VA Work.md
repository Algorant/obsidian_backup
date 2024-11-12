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
	- [x] ICN
		- Patient Member id?
	- [x] VISN in Blue
		- [ ] Acute Care Management: Breaks down 
		- VA Location
		- MemberId -> MemberFAcility -> RegionFacility -> Region
		- sproc: sel_FacilityByMemberId
		- VISN is superset, Site would be the actual facility (city)
			- Visn 11, could have miami and ft myers
	- [x] Site (managed group) in Red
		- MemberDetail.ManagedGroupId
		- MemberId -> ManagedGroupId
		- In above sproc there is information relating to managed group
	- [x] Platform in Purple
		- sproc: sel_DeviceRegistration
		- DeviceType for DeviceName
		- DeviceRegistration for DeviceRegistrationId
		- MemberId -> DeviceRegistration.DeviceRegistrationId, UnitID
		- Note: Ask James about headless hub for teleresponse (tele with vsrn)
	- [x] Primary DMP in Orange
		- sproc: sel_DeviceRegistration
		- Diabetes platform?
		- Needs DiseaseProgram (for program name),
		- Split out DMP from number (which is a date for version control() 
	- Comorbid DMP(s)
		- FlexComorbidity.[Id, Name, Abbrev, DiseaseProgramId]
		- Can be multiple things, separated by comma
	- [x] Media version in teal
		- DeviceRegistration.DeviceRegistrationID, DeviceRegistration.MemberID, DeviceRegistration.MediaVersion
	- [x] Firmware version in teal
		- DeviceRegistration.UnitVersion ??
		- Just a guess
	- [x] Care Coordinator in Green
		- Relationship.Profession (shows care coordinator)
		- Relationship.RelationshipId
		- Lots of Empty Values
		- Display as: First Name, Last name
		- Clarify logic for System Assigned CC, not the other one, verify with Jim
	- [ ] Category of Care
		- Look at screenshot
		- It's a VA term
	- Days on Service
		- ???
		- Will do Current Date - Enrollment Date in days
	- [x] Enrollment Date
		- MembersEnrolledInDateRange sproc
		- MemberEnrollment.MemberID, MemberEnrollment.ActionDate where ActionID = 1 for date range
	- [x] Disenrollment Date
		- MemberEnrollment where not 1 for date range
		- Enrollment Date - Disenrollment Date is DoS
	- [ ] Possible Edge Case
		- [ ] If previous enrollment, and also new enrollment, only keep most current

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
