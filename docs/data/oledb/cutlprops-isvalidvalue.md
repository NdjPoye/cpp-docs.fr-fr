---
title: "CUtlProps::IsValidValue | Microsoft Docs"
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
  - "CUtlProps::IsValidValue"
  - "CUtlProps.IsValidValue"
  - "IsValidValue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsValidValue (méthode)"
ms.assetid: 1164556e-8d98-429c-a396-fc9a699e0e97
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CUtlProps::IsValidValue
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisé pour valider une valeur avant de définir une propriété.  
  
## Syntaxe  
  
```  
  
      virtual HRESULT CUtlPropsBase::IsValidValue(  
   ULONG /* iCurSet */,  
   DBPROP* pDBProp   
);  
```  
  
#### Paramètres  
 `iCurSet`  
 L'index dans le tableau de propriété ; zéro s'il n'existe qu'un seul jeu de propriétés.  
  
 `pDBProp`  
 L'ID de propriété et une nouvelle valeur dans une structure [DBPROP](https://msdn.microsoft.com/en-us/library/ms717970.aspx).  
  
## Valeur de retour  
 Un `HRESULT` standard.  La valeur renvoyée par défaut est `S_OK`.  
  
## Notes  
 Si vous avez des routines de validation à effectuer sur une valeur que vous êtes sur le point d'utiliser pour définir une propriété, vous devez substituer cette fonction.  Par exemple, vous pouvez valider **DBPROP\_AUTH\_PASSWORD** sur une table de mot de passe pour déterminer une valeur valide.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [CUtlProps, classe](../../data/oledb/cutlprops-class.md)