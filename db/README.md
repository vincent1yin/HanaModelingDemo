Below Sql script used to  insert intial data into tables:
1. Usage of transparent filter flag:
      CV: ZCV_Trans_Filter_1.hdbcalculationview
          ZCV_Trans_Filter_2.hdbcalculationview
      Tables:
          ZT_EXAM_TRANS_FILTER.hdbtable
      Sql Script:
          create column table ZT_EXAM_TRANS_FILTER(day DATE,TNR NVARCHAR(10),TTYP NVARCHAR(10));
          insert into ZT_EXAM_TRANS_FILTER values ('2015-10-10','1','SL');
          insert into ZT_EXAM_TRANS_FILTER values ('2015-10-11','1','SL');
      Link:
         https://blogs.sap.com/2018/02/01/usage-of-transparent-filter-flag/
2. Usage of “Keep Flag”:
      CV:
          ZCV_Drinks_Receipt_Cube.hdbcalculationview
          ZCV_Drinks_Receipt_Cube_1.hdbcalculationview
      Tables:
          ZT_DRINKS_RECEIPT.hdbtable
      Sql Script:
          CREATE COLUMN TABLE "DRINKS_RECEIPT" (day Date, hour VARCHAR(2), PRODUCT NVARCHAR(40),AMOUNT Decimal(10,2), CONVERSIONRATE Decimal(4,2));
           INSERT INTO "DRINKS_RECEIPT" VALUES ('2017/02/02','10','Wine',30,1);
           INSERT INTO "DRINKS_RECEIPT" VALUES ('2017/02/02','18','Wine',20,2);
           INSERT INTO "DRINKS_RECEIPT" VALUES ('2017/02/02','10','Beer',40,1);
           INSERT INTO "DRINKS_RECEIPT" VALUES ('2017/02/02','10','Beer',50,3);
           INSERT INTO "DRINKS_RECEIPT" VALUES ('2017/02/03','10','Beer',30,2);
           INSERT INTO "DRINKS_RECEIPT" VALUES ('2017/02/03','18','Beer',40,1);
           INSERT INTO "DRINKS_RECEIPT" VALUES ('2017/02/03','11','Wine',50,2);
           INSERT INTO "DRINKS_RECEIPT" VALUES ('2017/02/03','19','Wine',100,3);
           INSERT INTO "DRINKS_RECEIPT" VALUES ('2017/02/03','20','MinearlWater',20,4);
           INSERT INTO "DRINKS_RECEIPT" VALUES ('2017/02/04','10','MineralWater',30,5);
           INSERT INTO "DRINKS_RECEIPT" VALUES ('2017/02/04','10','Wine',40,6); 
      Link:
         https://blogs.sap.com/2017/08/30/usage-of-keep-flag/
3.  Constant Selection in SAP HANA Using Dynamic Join
        CV:
          ZCV_Dynamic_Join_Demo.hdbcalculationview
        Tables:
          ZT_DYNAMIC_JOIN_DEMO.hdbtable
        Sql Script:
          Create Column TABLE "ZT_DYNAMIC_JOIN_DEMO"(COUNTRY VARCHAR2(20),COMPANY VARCHAR2(2),PRODUCT VARCHAR2(30),SELES Decimal(10,2));
          INSERT INTO "ZT_DYNAMIC_JOIN_DEMO" VALUES('US','A','Paper','100');
          INSERT INTO "ZT_DYNAMIC_JOIN_DEMO" VALUES('US','A','Envelopes','20');
          INSERT INTO "ZT_DYNAMIC_JOIN_DEMO" VALUES('US','A','Pens','30');
          INSERT INTO "ZT_DYNAMIC_JOIN_DEMO" VALUES('US','B','Paper','50');
          INSERT INTO "ZT_DYNAMIC_JOIN_DEMO" VALUES('US','B','Envelopes','40');
          INSERT INTO "ZT_DYNAMIC_JOIN_DEMO" VALUES('US','B','Pens','35');
          INSERT INTO "ZT_DYNAMIC_JOIN_DEMO" VALUES('US','C','Paper','72');
          INSERT INTO "ZT_DYNAMIC_JOIN_DEMO" VALUES('US','C','Envelopes','24');
          INSERT INTO "ZT_DYNAMIC_JOIN_DEMO" VALUES('US','C','Pens','39');
          INSERT INTO "ZT_DYNAMIC_JOIN_DEMO" VALUES('Canada','A','Paper','100');
          INSERT INTO "ZT_DYNAMIC_JOIN_DEMO" VALUES('Canada','A','Envelopes','20');
          INSERT INTO "ZT_DYNAMIC_JOIN_DEMO" VALUES('Canada','A','Pens','30');
          INSERT INTO "ZT_DYNAMIC_JOIN_DEMO" VALUES('Canada','B','Paper','50');
          INSERT INTO "ZT_DYNAMIC_JOIN_DEMO" VALUES('Canada','B','Envelopes','40');
          INSERT INTO "ZT_DYNAMIC_JOIN_DEMO" VALUES('Canada','B','Pens','35');
      Link:
         https://blogs.sap.com/2016/12/17/constant-selection-in-sap-hana-using-dynamic-join/
4.  Optimize Join columns/Join Pruning
        CV:
          ZCV_Optimize_Join_Columns.hdbcalculationview
        Tables:
          ZT_ITEMS_MD.hdbtable
          ZT_SALES_ITEMS.hdbtable
        Sql Script:
          CREATE COLUMN TABLE "ZT_ITEMS_MD"(item  NVARCHAR(30), description NVARCHAR(30));
          CREATE COLUMN TABLE "ZT_SALES_ITEMS"(item NVARCHAR(30),employee NVARCHAR(30), amount DECIMAL(10,2));
          insert into "ZT_ITEMS_MD" values ('001','diapers');
          insert into "ZT_ITEMS_MD" values ('002','diapers');
          insert into "ZT_ITEMS_MD" values ('003','milk');
          insert into "ZT_ITEMS_MD" values ('004','wine');
          insert into "ZT_SALES_ITEMS" values ('001','Donald',10);
          insert into "ZT_SALES_ITEMS" values ('002','Donald',50);
          insert into "ZT_SALES_ITEMS" values ('003','Alice',40);
          insert into "ZT_SALES_ITEMS" values ('004','Dagobert',21);
        Link:
           https://blogs.sap.com/2018/08/10/example-optimize-join-columns/
5.  Non Equi join in SAP HANA 2.0 Web IDE
        CV:
          ZCV_Employee_Non_EquiJoin.hdbcalculationview
        Tables:
          ZT_EMPLOYEE.hdbtable
        Sql Script:
           CREATE COLUMN TABLE ZT_EMPLOYEE( business_entity_id INTEGER ,first_name VARCHAR2(20) ,last_name VARCHAR2(20), primary k(business_entity_id,first_name,last_name));
           INSERT INTO "ZT_EMPLOYEE" VALUES('1','Subhas','Bose');
           INSERT INTO "ZT_EMPLOYEE" VALUES('1','Rabindranath','Tagore');
           INSERT INTO "ZT_EMPLOYEE" VALUES('1','Jon','Doe');
           INSERT INTO "ZT_EMPLOYEE" VALUES('2','Subhas','Bose');
           INSERT INTO "ZT_EMPLOYEE" VALUES('2','Subhendu','Ghanty');
           INSERT INTO "ZT_EMPLOYEE" VALUES('2','aaaa','bbbb');
        Link:
           https://blogs.sap.com/2019/12/31/non-equi-join-in-sap-hana-2.0-web-ide/
6.  Cube Star Join
        CV:
           ZCV_STAR_JOIN_TEST.hdbcalculationview
         Tables:
           ZT_Cube_Empdate.hdbtable
           ZT_Cube_Empdim.hdbtable
           zt_cube_Empfact1.hdbtable
           zt_cube_Empfact2.hdbtable
         Sql Script:
           /* This Dimension table is Employee name table (haveEmpId and EmpName) */
           drop table ZT_cube_Empdim;
           create column table ZT_cube_Empdim (empId nvarchar(3) ,Empname nvarchar(20));
           insert into ZT_cube_Empdim values(‘A1’,‘Shivaji’);
           insert into ZT_cube_Empdim values(‘B1’,‘Anand’);
           insert into ZT_cube_Empdim values(‘C1’,‘Stephan’);
           /* This Dimension table is  a calendar table (date,month and year) */
           drop table zt_cube_Empdate;
           create column table zt_cube_Empdate (caldate  date,CALMONTH nvarchar(4) ,CALYEAR nvarchar(4));
           insert into zt_cube_Empdate values(‘20100101’,’01’,‘2010’);
           insert into zt_cube_Empdate values(‘20110101’,’02’,‘2011’);
           insert into zt_cube_Empdate(‘20120101’,’03’,‘2012’);
              ——————————————–FACT Tables —————————————-
            /* This Fact table describes Employee Salary */
            drop table zt_cube_Empfact1;
            Create column table zt_cube_Empfact1 (empId nvarchar(3), Empdate date, Sal integer );
            insert into  zt_cube_Empfact1 values(‘A1’,‘20100101’,4000);
            insert into  zt_cube_Empfact1 values(‘B1’,‘20110101’,6000);
            insert into  zt_cube_Empfact1 values(‘C1’,‘20120101’,8000);
            /* This Fact table describes Employee Bonus */
            drop table zt_cube_Empfact2;
            Create column zt_cube_Empfact2 Empfact2 (empId nvarchar(3), deptName nvarchar(20), Bonus integer );
            insert into zt_cube_Empfact2 values(‘A1’,‘SAP’,1000);
            insert into zt_cube_Empfact2 values(‘B1’,‘NS2’,2000);
            insert into zt_cube_Empfact2 values(‘C1’,‘SAPAG’,3000);
         Link:
             https://blogs.sap.com/2014/02/13/hana-sp07-star-join/
7.  Calling Table functions in SAP HANA calculation views
    CV:
        ZCV_Table_Function_Demo.hdbcalculationview
    TF:
        ZTF_Demo.hdbfunction
    Sql Script:
        Function ZTF_Demo (IP_ENTITYID Integer)
           returns TABLE(
              first_name Varchar2(10),
              last_name  Varchar2(10)
              )
           LANGUAGE SQLSCRIPT
           SQL SECURITY INVOKER AS
           BEGIN
             RETURN
                select
                   first_name, last_name from ZT_EMPLOYEE where business_entity_id =:IP_ENTITYID;
           END;
    Link:
        https://blogs.sap.com/2018/11/05/table-functions-in-sap-hana-step-by-step-guide/
8.  Create Window Function
    CV:
      ZCV_Window_Function.hdbcalculationview
9.  Create Time Dimension:
    CV:

    Tables:

    Script:

    Link:
        
      




       