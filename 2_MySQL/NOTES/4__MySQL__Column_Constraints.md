# Constraints / Restrictions 

1. `NOT NULL` : Dosent Allow Null / Empty Values
2. `DEFAULT` : Sets Default Value When Not Mentioned
3. `UNIQUE` : Makes Sure the Values are Not Repeated
4. `PRIMARY KEY` : UNIQUE + NOT NULL + INDEX
5. `AUTO_INCREMENT` : Automatically increments a integer
6. `FOREIGN KEY` : References columns in other tables
   1. References Other Column of **Same** or **Different** Tables
   2. Linking Records
   3. Eg.
      1. Followers / Following
         1. user1 --- follows ---- user2
         2. user1 --- follows ---- user3
7. `CHECK` : Manual Constraints
   1. `CHECK  ((age > 16) AND (age < 20))`
8. `ENUM / SET` : Allows only specified Values

