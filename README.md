SELECT DISTINCT HM.ID_HKMLK, IM.TRKH_DAFTAR, IV.CATATAN		
,TRIM(REPLACE(IV.CATATAN, SUBSTR(IV.CATATAN,1,INSTR(IV.CATATAN,'-')))) KOD_URSN		
,(SELECT NAMA FROM IND_URSN IU WHERE KOD = (TRIM(REPLACE(IV.CATATAN, SUBSTR(IV.CATATAN,1,INSTR(IV.CATATAN,'-'))))) ) URSN		
FROM  IND_HKMLK HM		
JOIN IND_VERSI_DHD IV ON HM.HKMLK_ID = IV.HKMLK_ID AND IV.FLAG_AKTIF ='Y'		
JOIN IND_MKLMT_HKMLK IM ON IM.MKLMT_HKMLK_ID = IV.MKLMT_HKMLK_ID		
WHERE HM.ID_HKMLK in ('110420HSM00001199'
'110606GM00020414',
'110606GM00020413',
'110606GM00020415',
'110606GM00020416',
'110606GM00020417',
'110606GM00020418',
'110606GM00020419',
'110606GM00020420',
'110606GM00020421',
'110606GM00020422'
);		
