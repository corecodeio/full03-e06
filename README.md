# Oracle Commands

## Open PDB And Save State

```
  $ sqlplus / as sysdba
  $ alter pluggable database ORCLPDB open;
  $ alter pluggable database ORCLPDB save state;
  $ select con_name, state from dba_pdb_saved_states;
```

## Create user in PDB

```
  $ sqlplus / as sysdba
  $ ALTER SESSION SET CONTAINER = orclpdb;
  $ CREATE USER <username> IDENTIFIED BY <password> CONTAINER=CURRENT;
  $ GRANT ALL PRIVILEGES TO <username> CONTAINER=CURRENT;
  $ ALTER USER <username> DEFAULT TABLESPACE users TEMPORARY TABLESPACE temp QUOTA UNLIMITED ON users;
```

## Queries

```sql

-- DUAL

SELECT (1+1) FROM DUAL;

-- CRATE USER TABLE

CREATE TABLE PERSON (
	PERSON NUMBER,
	FIRST_NAME VARCHAR2(100) NOT NULL,
	EMAIL VARCHAR2(100) NOT NULL,
	PASSWORD VARCHAR2(100) NOT NULL,
	ADD_DATE DATE DEFAULT SYSDATE,
	PRIMARY KEY(PERSON)
);

SELECT * FROM PERSON;




```
