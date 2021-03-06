발제자 : 심민규

## 예제

```
IF EXISTS(SELECT 1 FROM sys.tables WHERE object_id = OBJECT_ID('myTable'))
BEGIN;
    DROP TABLE [myTable];
END;
GO

CREATE TABLE [myTable] (
    [myTableID] INTEGER NOT NULL IDENTITY(1, 1),
    [USR_NAME] VARCHAR(255) NULL,
    [USR_EMAIL] VARCHAR(255) NULL,
    [DEL_YN] VARCHAR(MAX) NULL,
    [USR_COMP] VARCHAR(255) NULL,
    [USR_CITY] VARCHAR(255) NULL
);
GO

INSERT INTO myTable([USR_NAME],[USR_EMAIL],[DEL_YN],[USR_COMP],[USR_CITY]) VALUES('Hiroko','Aenean@sitametmassa.com','Y','Eget Ipsum Donec Consulting','Hoeilaart');
INSERT INTO myTable([USR_NAME],[USR_EMAIL],[DEL_YN],[USR_COMP],[USR_CITY]) VALUES('Trevor','risus.Donec.egestas@Nuncquis.ca','Y','Pellentesque Habitant Company','Wanganui');
INSERT INTO myTable([USR_NAME],[USR_EMAIL],[DEL_YN],[USR_COMP],[USR_CITY]) VALUES('Ila','pharetra.sed@rutrumloremac.net','Y','A Scelerisque Corporation','Callander');
INSERT INTO myTable([USR_NAME],[USR_EMAIL],[DEL_YN],[USR_COMP],[USR_CITY]) VALUES('Arthur','Etiam.bibendum.fermentum@egestasFuscealiquet.ca','Y','Sed Consulting','Bossut-Gottechain');
INSERT INTO myTable([USR_NAME],[USR_EMAIL],[DEL_YN],[USR_COMP],[USR_CITY]) VALUES('Christopher','Morbi.sit@fringillaornareplacerat.ca','Y','Vestibulum Accumsan Neque PC','Mellet');
INSERT INTO myTable([USR_NAME],[USR_EMAIL],[DEL_YN],[USR_COMP],[USR_CITY]) VALUES('Erica','ante.dictum.cursus@adui.org','Y','Fringilla Donec Feugiat LLP','Jelenia Góra');
INSERT INTO myTable([USR_NAME],[USR_EMAIL],[DEL_YN],[USR_COMP],[USR_CITY]) VALUES('Fulton','interdum.Nunc@sedturpisnec.org','Y','Sem Nulla Corp.','Deline');
INSERT INTO myTable([USR_NAME],[USR_EMAIL],[DEL_YN],[USR_COMP],[USR_CITY]) VALUES('Yuri','Etiam@Duissit.edu','Y','Mauris Blandit Corporation','Flushing');
INSERT INTO myTable([USR_NAME],[USR_EMAIL],[DEL_YN],[USR_COMP],[USR_CITY]) VALUES('Jasper','Nulla.aliquet@eget.ca','Y','Iaculis Odio Foundation','Cochrane');
INSERT INTO myTable([USR_NAME],[USR_EMAIL],[DEL_YN],[USR_COMP],[USR_CITY]) VALUES('TaShya','Etiam.bibendum.fermentum@vel.co.uk','Y','Et Incorporated','Vitrolles');
INSERT INTO myTable([USR_NAME],[USR_EMAIL],[DEL_YN],[USR_COMP],[USR_CITY]) VALUES('Martena','Quisque.imperdiet.erat@urnasuscipit.org','N','Mus Aenean Industries','Lalbahadur Nagar');



SELECT * FROM mytable --전체검색
WHERE USR_COMP = 'Proin PC' AND DEL_YN = 'Y'

/* Clustered Index */
DROP INDEX SRM.myTable.IX_mytable_00

CREATE CLUSTERED INDEX IX_mytable_00
ON SRM.myTable (myTableID)


/* NON Clustered Index */
DROP INDEX SRM.myTable.IX_mytable_01

CREATE NONCLUSTERED INDEX IX_mytable_01
ON SRM.myTable (USR_COMP, DEL_YN )

/* NON Clustered Index with include */
DROP INDEX SRM.myTable.IX_mytable_01

CREATE NONCLUSTERED INDEX IX_mytable_01
ON SRM.myTable (USR_COMP )
INCLUDE (USR_NAME, USR_EMAIL, DEL_YN)

SELECT USR_NAME, USR_EMAIL FROM mytable --전체검색
WHERE USR_COMP = 'Proin PC' AND DEL_YN = 'Y'

```