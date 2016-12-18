---
title: "CDBVariant Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDBVariant"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDBVariant (classe)"
  - "Variant (types de données), ODBC"
ms.assetid: de23609c-c560-4b24-bd6b-9d8903fd5b49
caps.latest.revision: 21
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDBVariant Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente un type de données variant pour les classes ODBC MFC.  
  
## Syntaxe  
  
```  
class CDBVariant  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDBVariant::CDBVariant](../Topic/CDBVariant::CDBVariant.md)|Construit un objet `CDBVariant`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDBVariant::Clear](../Topic/CDBVariant::Clear.md)|Efface l'objet d' `CDBVariant` .|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDBVariant::m\_dwType](../Topic/CDBVariant::m_dwType.md)|Contient le type de données de la valeur actuellement stockée.  Tapez `DWORD`|  
  
### Travailleurs syndiqués publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDBVariant::m\_boolVal](../Topic/CDBVariant::m_boolVal.md)|Contient une valeur de type **BOOL**.|  
|[CDBVariant::m\_chVal](../Topic/CDBVariant::m_chVal.md)|Contient une valeur de type `unsigned char`.|  
|[CDBVariant::m\_dblVal](../Topic/CDBVariant::m_dblVal.md)|Contient une valeur de type **double**.|  
|[CDBVariant::m\_fltVal](../Topic/CDBVariant::m_fltVal.md)|Contient une valeur de type **float**.|  
|[CDBVariant::m\_iVal](../Topic/CDBVariant::m_iVal.md)|Contient une valeur de type **short**.|  
|[CDBVariant::m\_lVal](../Topic/CDBVariant::m_lVal.md)|Contient une valeur de type **long**.|  
|[CDBVariant::m\_pbinary](../Topic/CDBVariant::m_pbinary.md)|Contient un pointeur vers un objet de type `CLongBinary`.|  
|[CDBVariant::m\_pdate](../Topic/CDBVariant::m_pdate.md)|Contient un pointeur vers un objet de type **TIMESTAMP\_STRUCT**.|  
|[CDBVariant::m\_pstring](../Topic/CDBVariant::m_pstring.md)|Contient un pointeur vers un objet de type `CString`.|  
|[CDBVariant::m\_pstringA](../Topic/CDBVariant::m_pstringA.md)|Stocke un pointeur vers un objet ASCII de [CString](../../atl-mfc-shared/reference/cstringt-class.md) .|  
|[CDBVariant::m\_pstringW](../Topic/CDBVariant::m_pstringW.md)|Stocke un pointeur vers un objet niveau de [CString](../../atl-mfc-shared/reference/cstringt-class.md) .|  
  
## Notes  
 `CDBVariant` n'a pas de classe de base.  
  
 `CDBVariant` est semblable à [COleVariant](../../mfc/reference/colevariant-class.md); toutefois, `CDBVariant` n'utilise pas OLE.  `CDBVariant` vous permet de stocker une valeur sans vous préoccuper du type de données de la valeur.  `CDBVariant` suit le type de données de la valeur actuelle, qui est stocké dans une union.  
  
 La classe [CRecordset](../../mfc/reference/crecordset-class.md) utilise des objets d' `CDBVariant` dans les fonctions composées de trois membres : `GetFieldValue`, `GetBookmark`, et `SetBookmark`.  Par exemple, `GetFieldValue` vous permet de manière dynamique aux données d'effort dans une colonne.  Étant donné que le type de données de la colonne ne peut être connu au moment de l'exécution, `GetFieldValue` utilise un objet d' `CDBVariant` pour stocker les données de la colonne.  
  
## Hiérarchie d'héritage  
 `CDBVariant`  
  
## Configuration requise  
 **Header:** afxdb.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)   
 [CRecordset::GetFieldValue](../Topic/CRecordset::GetFieldValue.md)   
 [CRecordset::GetBookmark](../Topic/CRecordset::GetBookmark.md)   
 [CRecordset::SetBookmark](../Topic/CRecordset::SetBookmark.md)