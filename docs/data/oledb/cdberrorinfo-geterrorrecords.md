---
title: "CDBErrorInfo::GetErrorRecords | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDBErrorInfo.GetErrorRecords"
  - "ATL.CDBErrorInfo.GetErrorRecords"
  - "ATL::CDBErrorInfo::GetErrorRecords"
  - "GetErrorRecords"
  - "CDBErrorInfo::GetErrorRecords"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetErrorRecords (méthode)"
ms.assetid: 07746774-bcca-4833-8f55-a619e9777c17
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDBErrorInfo::GetErrorRecords
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient les enregistrements d'erreurs pour l'objet spécifié.  
  
## Syntaxe  
  
```  
  
      HRESULT GetErrorRecords(   
   IUnknown* pUnk,   
   const IID& iid,   
   ULONG* pcRecords    
) throw( );  
HRESULT GetErrorRecords(   
   ULONG* pcRecords    
) throw( );  
```  
  
#### Paramètres  
 *pUnk*  
 \[in\] interface sur l'objet pour lequel obtenir des enregistrements d'erreur.  
  
 `iid`  
 \[in\] IID de l'interface associée à l'erreur.  
  
 *pcRecords*  
 \[out\] Un pointeur vers le compteur \(de base 1\) d'enregistrements d'erreur.  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Notes  
 Utilisez la première forme de la fonction si vous souhaitez activer l'interface pour obtenir des informations sur l'erreur.  Sinon, utilisez le second format.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDBErrorInfo, classe](../../data/oledb/cdberrorinfo-class.md)