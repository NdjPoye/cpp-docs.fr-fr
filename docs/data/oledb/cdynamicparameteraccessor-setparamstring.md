---
title: "CDynamicParameterAccessor::SetParamString | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CDynamicParameterAccessor.SetParamString"
  - "ATL::CDynamicParameterAccessor::SetParamString"
  - "SetParamString"
  - "CDynamicParameterAccessor::SetParamString"
  - "CDynamicParameterAccessor.SetParamString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetParamString (méthode)"
ms.assetid: 77a38d23-7e33-4e5a-bda6-c12c4c3fe2e4
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicParameterAccessor::SetParamString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit les données de chaîne du paramètre stocké en mémoire tampon.  
  
## Syntaxe  
  
```  
  
      bool SetParamString(   
   DBORDINAL nParam,   
   const CHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK    
) throw( );  
bool SetParamString(   
   DBORDINAL nParam,   
   const WCHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK    
) throw( );  
```  
  
#### Paramètres  
 `nParam`  
 \[in\] Le nombre de paramètre \(décalage de 1\).  Le paramètre 0 est réservé pour les valeurs de retour.  Le numéro de paramètre représente l'index du paramètre en fonction de son ordre dans l'appel SQL ou celui d'une procédure stockée.  Consultez [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) pour obtenir un exemple.  
  
 `pString`  
 \[in\] Un pointeur vers les données de chaîne ANSI \(**CHAR**\) ou Unicode \(**WCHAR**\) du paramètre.  Voir `DBSTATUS` dans oledb.h.  
  
 *status*  
 \[in\] L'état `DBSTATUS` du paramètre spécifié.  Pour plus d'informations sur les valeurs de `DBSTATUS`, consultez l'[État](https://msdn.microsoft.com/en-us/library/ms722617.aspx) dans *OLE DB guide de référence du programmeur*, ou recherchez dans `DBSTATUS` oledb.h.  
  
## Notes  
 Retourne la valeur **vrai** en cas de réussite, ou **faux** en cas d'échec.  
  
 `SetParamString` échouera si vous essayez de définir une chaîne qui dépasse la taille maximale pour `pString`.  
  
 Utilisez`SetParamString` pour définir les paramètre de chaîne dans la mémoire tampon.  Utilisez [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) pour définir les données qui ne sont pas de type chaîne en mémoire tampon.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDynamicParameterAccessor, classe](../../data/oledb/cdynamicparameteraccessor-class.md)