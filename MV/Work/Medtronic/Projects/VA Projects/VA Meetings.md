#### 08/13/2024 [[VA Work]] Meeting with Mallory, James Rivord, Kyle Bender
##### The Ask
- The situation
	- I currently don't have access
	- the migration itself is delayed until next year, etc
	- meeting with todd hanson and Barrett as far as what I am able to do
	- a little opaque and particular, given the specific asks that I get
	- In your opinion, can mallory give us an ask like this?
- This is the ask
	- Active, Enrollments, Disenrollments
	- Run for 1st of each Month
	- Mutually exclusive
- Questions
	- HL7 vs just OPro itself?
	- Can I get access to opro?
	- Can someone, say mallory, send me this and then I organize it?
	- Do I technically need to do a formal procedure, for this
	- Is Tableau approved to run in VA?
	- Demo of tableau features and uses
- Next steps
	- bounce off [[Mallory]], make sure it makes sense to her
	- seeing what I can do from dev (cubes? modular, etc?)
	- tableau functionality from within 

##### Fields Needed
- ICN
- VISN (VA Facility I think?)
- Site (Managed Group)
- Platform
- Primary DMP
- Comorbid DMP
- Media Version
- Firmware Version
- Care Coordinator
- Category of Care
- Days on Service
- Enrollment Date
- Disenrollment Date
##### Relevant Tables
- Relevant Primary Tables
	- MemberStatusID has
		- MemberID, StatusId, Begin/End Date, FacilityID, Note
	- MemberID has
		- MemberId, ActiveDate, InactiveDate, InactiveReasonId
	- MemberEnrollment has
		- EnrollmentId, MemberId, ActionId, ActionDate, InactiveReason
- Relevant Secondary Tables
	- InactiveReason
		- Lookup for InactiveReasonId

#### 2024-09-17 [[VA Work]] with Devops, Mallory, and etc.
- 