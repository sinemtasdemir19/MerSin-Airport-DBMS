# MerSin  Airport - Database  Management  System
The aim of this project is to establish an airport database, which is essential for effective **airport management**. By successfully creating this database, Mersin Airport can now be efficiently managed, ensuring smooth operations and eliminating any potential issues.

## Business  Rules
1.  Airport has name, address, country and city information. Each airport has different id  number.
2.  An airport must have at least one employee but there can also be more than one  employee.  An  employee  must  work  only  one  airport.
3.  Employee information should include name, surname, gender, and year of  experience.  Each  employee  has  different id  number.
4.  Employees can be a manager, security, cleaning staff member, passenger service  officer, or other personnel. But it can be only one of them. If an employee is a  security, used gun information should be kept, and if an employee is a passenger  service officer,  work  area  information should  also  be  kept.
5.  An airport has at least one airfield or more than one. An airfield must belong only  one airport.
6. Airfield  has  length  information.  Each  airfield  has  different  id  number.
7.  An airport has at least one plane or more than one. A plane must belong only one  airport or  none.
8.  Plane has blade type, engine type, weight and fuel type information. Each plane has  different id  number.
9.  Planes can be a passenger, cargo, military, firefighting or other type of planes. But it  can be only one of them. If a plane is a passenger plane; number of seat and number  of stewardess information should be kept. If a plane is a cargo plane; capacity  information should be kept. If a plane is a military plane; number of seats, equipment  and number of military information should be kept and if a plane is a firefighting  plane; tank  capacity  and  number  of  fireman information  should  also  be  kept.
10. A pilot can  fly  a  plane  or  many  plane.  A  plane can  be  flown  by  one  pilot  or  more  than  one  pilot.
11.  Pilot information should include name, surname, gender, and year of experience.  Each pilot  has  different  id  number.
12.  Pilots must be only one of the categories, chief or co-pilot. There can not be other  pilot  in  the  system.
13.  A  plane agent  can  have  no  pilot  or many  pilots.  A  pilot  must  work  for one  plane  agent.
14.  Plane  agent  has  name,  number  of  plane,  number  of employee  information.  Each  plane  agent  has  different  id  number.
15.  A stewardess can work for only one plane agent. A plane agents can have no  stewardess  or  many stewardesses.
16.  Stewardess information should include name, surname, gender, and year of  experience.  Each stewardess has  different  id number.
17.  In the system, a stewardess can exist in just two categories: a domestic and an  international.  A  stewardess can  also  be both.
18.  A stewardess can work a passenger plane or many passenger plane. A passenger  plane  can have  one  stewardess  or  more  than  one stewardess.
19.  A plane agent should have at least one passenger plane or more than one. A  passenger  plane  must  belong only  one  plane  agent.
20.  A passenger plane may not take a flight or may have more than one flight. A flight  can only  have  one passenger  plane.
21.  Flight information should include date, hour, and number of booked seat. Each flight  has  different  id  number.
22.  A flight should belong only one airport. An airport should have at least one flight or  more  than  one.
24.  A flight should belong only one passenger plane. A passenger plane can have no flight  or  many.
25.  A  flight can  have  no  ticket or  many  tickets.  A  ticket  can  only  belong one  flight.
26.  Ticket information should include seat number, price. Each ticket has different id  number.
27.  Tickets must be only one of the two categories, economic and business. There can  not  be  other  tickets  in  the  system.
28.  A  ticket  can  book  by  only  one  passenger,  a  passenger can  book  a  ticket  or  no  ticket.
29.  Passenger information should include name, surname, gender, age, and identity  number.  Each  passenger  has different id  number.
30.  A passenger can have no baggage or many baggage. A baggage should belong only  one  passenger.
31. Baggage information should include weight, and type. Each baggage has different id  number.</br>

## Entity  Relationship Model
![](MerSinLizbon.drawio.png)

## Relational Model 
**Airport** (AirportID: varchar, Name: varchar, Country: varchar, City: varchar, Address: varchar)</br>
**Airfield** (AirfieldID: serial, Length: integer, AirportID: varchar)</br>
**Passenger** (PassengerID: serial, Name: varchar, Surname: varchar, Gender: char(1), Age: integer, IdentityNumber: integer(11))</br>
**Baggage** (BaggageID: serial, Type: varchar, Weight: integer, PassagnerID: serial)</br>
**PlaneAgent** (PlaneAgentID: integer, Name: varchar, NumberOfPlane: integer, NumberOfEmployee: integer)</br>
**Employee** (EmployeeID: serial, Name: varchar, Surname: varchar, Gender: char(1), YearOfExperience: integer, AirportID: varchar, EmployeeType: char(1))</br>
**Manager** (EmployeeID: serial)</br>
**Security** (EmployeeID: serial, UseGun: boolean)</br>
**PassengerServiceOfficer** (EmployeeID: serial, WorkArea: varchar)</br>
**CleaningStaffMember** (EmployeeID: serial, Company: varchar)</br>
**Plane** (PlaneID: serial, BladeType: varchar, EngineType: varchar, FeulType: varchar, Weight: integer, AirportID: varchar, PlaneType: char(1)) </br>
**MilitaryPlane** (PlaneID: serial, Equipment: boolean, NumberOfSeat: integer, NumberOfMilitary: integer)</br>
**FireFightingPlane** (PlaneID: serial, TankCapacity: integer, NumberOfFireman: integer)</br>
**CargoPlane** (PlaneID: serial, Capacity:integer)</br>
**PassangerPlane** (PlaneID: serial, NumberOfStewardess: integer, NumberOfSeat: integer, PlaneAgentID: integer)</br>
**Flight** (FlightID: serial, Date: date, NumberOfBookedSeat: integer, AirportID: varchar)</br>
**Ticket** (TicketID: serial,  SeatNumber: varchar, Price: integer, PassengerID: serial, FlightID: serial, TicketType: char(1))</br>
**EconomicTicket** (TicketID: serial)</br>
**BusinessTicket** (TicketID: serial)</br>
**Pilot** (PilotID: serial, Name: varchar, Surname: varchar, Gender: char(1), YearOfExperience: integer, PlaneAgentID: integer, PilotType: char(1))</br>
**ChiefPilot** (PilotID: serial)</br>
**co-Pilot** (PilotID: serial)</br>
**PlanePilot** (PlaneID: serial, PilotID: serial)</br>
**Stewardess** (StewardessID: serial, Name: varchar, Surname: varchar, Gender: char(1), YearOfExperience: integer, PlaneAgentID: integer, StewardessType: char(1))</br>
**Domestic** (StewardessID: serial)</br>
**International** (StewardessID: serial)</br>
**PassangerPlaneStewardess** (PlaneID: serial, StewardessID: serial)</br>

## Screenshots of Application

### Search
<img width="454" alt="Picture1" src="https://github.com/user-attachments/assets/6c9d23c5-32df-4add-93df-2d51203458d4"></br>
### Insert
<img width="454" alt="Picture2" src="https://github.com/user-attachments/assets/5018efaa-7a56-4d14-b465-8f628afba525"></br>
<img width="454" alt="Picture3" src="https://github.com/user-attachments/assets/2b7ae744-3fa5-4bf1-896a-a9aada09277c"></br>
### Update
<img width="454" alt="Picture4" src="https://github.com/user-attachments/assets/879621c7-88ca-45cf-8a28-1880cecd6a31"></br>
<img width="454" alt="Picture5" src="https://github.com/user-attachments/assets/cc7c9f1c-8b35-4a2e-8d16-fe4c41d803bf"></br>
### Delete
<img width="454" alt="Picture6" src="https://github.com/user-attachments/assets/1fb123b8-1aa8-4e7d-8c19-16386095a0fb"></br>
<img width="454" alt="Picture7" src="https://github.com/user-attachments/assets/5a23aebe-cd7c-4225-99e6-a6054098030f">
