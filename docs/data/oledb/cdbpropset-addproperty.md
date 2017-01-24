---
title: "CDBPropSet::AddProperty | Microsoft Docs"
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
  - "CDBPropSet::AddProperty"
  - "CDBPropSet.AddProperty"
  - "AddProperty"
  - "ATL::CDBPropSet::AddProperty"
  - "ATL.CDBPropSet.AddProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddProperty (méthode)"
ms.assetid: dc9539d3-1ee4-40f3-9281-2068e6d65e93
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDBPropSet::AddProperty
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ajoute une propriété au jeu de propriétés.  
  
## Syntaxe  
  
```  
  
      bool AddProperty(   
   DWORD dwPropertyID,   
   const VARIANT& var,   
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   LPCSTR szValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   LPCWSTR szValue,   
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   bool bValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   BYTE bValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   short nValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   long nValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   float fltValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   double dblValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   CY cyValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
```  
  
#### Paramètres  
 *dwPropertyID*  
 \[in\] L'ID de la propriété à ajouter.  Utilisé pour initialiser **dwPropertyID** de la structure de `DBPROP` ajouté au jeu de propriétés.  
  
 `var`  
 \[in\] la variante utilisée pour initialiser la valeur de la propriété de la structure de `DBPROP` est ajoutée au jeu de propriétés.  
  
 `szValue`  
 \[in\] la chaîne utilisée pour initialiser la valeur de la propriété de la structure de `DBPROP` est ajoutée au jeu de propriétés.  
  
 `bValue`  
 \[in\] Un **BYTE** ou une valeur booléenne utilisée pour initialiser la valeur de la propriété de la structure de `DBPROP` ajouté au jeu de propriétés.  
  
 `nValue`  
 \[in\] Une valeur entière est utilisée pour initialiser la valeur des propriétés pour la structure `DBPROP` ajoutée à l'ensemble de propriétés.  
  
 *fltValue*  
 \[in\] Une valeur de point flottant utilisé pour initialiser la valeur de la propriété pour la structure `DBPROP` ajouté à l'ensemble de propriétés.  
  
 `dblValue`  
 \[in\] Une valeur de précision double d'un point flottant utilisée pour initialiser la valeur de la propriété pour la structure `DBPROP` ajouté à l'ensemble de propriétés.  
  
 `cyValue`  
 \[in\] Une valeur CY currency utilisée pour initialiser la valeur de la propriété pour la structure `DBPROP` ajouté à l'ensemble de propriétés.  
  
## Valeur de retour  
 **vrai** si la propriété a été ajouté avec succès.  sinon, **false**.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDBPropSet, classe](../../data/oledb/cdbpropset-class.md)   
 [DBPROP Structure](https://msdn.microsoft.com/en-us/library/ms717970.aspx)