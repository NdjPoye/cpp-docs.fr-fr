---
title: "CDynamicParameterAccessor::SetParam | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CDynamicParameterAccessor::SetParam"
  - "ATL::CDynamicParameterAccessor::SetParam<ctype>"
  - "CDynamicParameterAccessor.SetParam"
  - "ATL.CDynamicParameterAccessor.SetParam"
  - "SetParam"
  - "CDynamicParameterAccessor:SetParam"
  - "CDynamicParameterAccessor::SetParam<ctype>"
  - "CDynamicParameterAccessor::SetParam"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetParam (méthode)"
ms.assetid: e2349220-545c-46ad-90da-9113ac52551a
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CDynamicParameterAccessor::SetParam
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit la mémoire tampon de paramètre à l'aide de les données spécifiées \(non string\).  
  
## Syntaxe  
  
```  
  
      template < class   
      ctype >  
bool SetParam(  
   DBORDINAL nParam,  
   const ctype* pData,  
   DBSTATUS status = DBSTATUS_S_OK  
) throw( );  
template < class ctype >  
bool SetParam(  
   TCHAR* pParamName,  
   const ctype* pData,  
   DBSTATUS status = DBSTATUS_S_OK  
) throw( );  
```  
  
#### Paramètres  
 `ctype`  
 Un paramètre basé sur des modèles qui est le type de données.  
  
 `nParam`  
 \[in\] Le nombre de paramètre \(décalage de 1\).  Le paramètre 0 est réservé pour les valeurs de retour.  Le numéro de paramètre représente l'index du paramètre en fonction de son ordre dans l'appel SQL ou celui d'une procédure stockée.  Par exemple :  
  
 [!code-cpp[NVC_OLEDB_Consumer#8](../../data/oledb/codesnippet/CPP/cdynamicparameteraccessor-setparam_1.cpp)]  
  
 `pParamName`  
 \[in\] Nom du paramètre.  
  
 `pData`  
 \[in\] Le pointeur vers la mémoire contenant les données à écrire dans la mémoire tampon.  
  
 *status*  
 \[in\] La colonne d'état `DBSTATUS` .  Pour plus d'informations sur les valeurs de `DBSTATUS`, consultez [État](https://msdn.microsoft.com/en-us/library/ms722617.aspx) dans *OLE DB guide de référence du programmeur*, ou recherchez dans `DBSTATUS` oledb.h.  
  
## Valeur de retour  
 Retourne la valeur **vrai** en cas de réussite, ou **faux** en cas d'échec.  
  
 Utilisez `SetParam` pour définir les paramètre de type non\-chaîne dans la mémoire tampon.  Utilisez [SetParamString](../../data/oledb/cdynamicparameteraccessor-setparamstring.md) pour définir les paramètre de chaîne dans la mémoire tampon.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDynamicParameterAccessor, classe](../../data/oledb/cdynamicparameteraccessor-class.md)