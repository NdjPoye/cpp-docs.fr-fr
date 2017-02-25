---
title: "CDBErrorInfo::GetAllErrorInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CDBErrorInfo.GetAllErrorInfo"
  - "CDBErrorInfo::GetAllErrorInfo"
  - "ATL::CDBErrorInfo::GetAllErrorInfo"
  - "GetAllErrorInfo"
  - "CDBErrorInfo.GetAllErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetAllErrorInfo (méthode)"
ms.assetid: 630049fa-d296-497a-bbf6-f5d3d71d271d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CDBErrorInfo::GetAllErrorInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Renvoie tous les types d'informations d'erreur contenus dans un enregistrement d'erreur.  
  
## Syntaxe  
  
```  
  
      HRESULT GetAllErrorInfo(  
   ULONG ulRecordNum,  
   LCID lcid,  
   BSTR* pbstrDescription,  
   BSTR* pbstrSource = NULL,  
   GUID* pguid = NULL,  
   DWORD* pdwHelpContext = NULL,  
   BSTR* pbstrHelpFile = NULL  
) const throw( );  
```  
  
#### Paramètres  
 *ulRecordNum*  
 \[in\] au numéro de base zéro de la journalisation pour lequel renvoyer des informations d'erreur.  
  
 `lcid`  
 \[in\] ID de paramètres régionaux pour obtenir des informations sur l'erreur sont retournées.  
  
 `pbstrDescription`  
 \[out\] pointeur à une description de l'erreur ou NULL si les paramètres régionaux ne sont pas pris en charge.  Consultez la section Notes.  
  
 `pbstrSource`  
 \[out\] pointeur d'Un en une chaîne contenant le nom du composant qui a généré l'erreur.  
  
 `pguid`  
 \[out\] pointeur à le GUID de l'interface qui a défini l'erreur.  
  
 *pdwHelpContext*  
 \[out\] pointeur à l'ID de contexte d'aide pour l'erreur.  
  
 *pbstrHelpFile*  
 \[out\] pointeur d'Un en une chaîne qui contient le chemin d'accès au fichier d'aide qui décrit l'erreur.  
  
## Valeur de retour  
 `S_OK` en cas de réussite.  Consultez [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx) dans *OLE DB guide de référence du programmeur* d'autres valeurs de retour.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Notes  
 La valeur de sortie de `pbstrDescription` est obtenue en interne en appelant IErrorInfo::GetDescription, qui définit la valeur null si les paramètres régionaux ne sont pas pris en charge, ou si les deux conditions suivantes sont remplies :  
  
1.  la valeur de `lcid` n'est PAS de l'anglais des Etats\-Unis et  
  
2.  la valeur de `lcid` n'est PAS égale à la valeur renvoyée par GetUserDefaultLCID.  
  
## Voir aussi  
 [CDBErrorInfo, classe](../../data/oledb/cdberrorinfo-class.md)