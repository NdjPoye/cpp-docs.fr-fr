---
title: "CDynamicParameterAccessor::GetParamString | Microsoft Docs"
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
  - "CDynamicParameterAccessor.GetParamString"
  - "GetParamString"
  - "CDynamicParameterAccessor::GetParamString"
  - "ATL.CDynamicParameterAccessor.GetParamString"
  - "ATL::CDynamicParameterAccessor::GetParamString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetParamString (méthode)"
ms.assetid: 078c2b1c-7072-47c1-a203-f47e75363f91
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicParameterAccessor::GetParamString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère les données de chaîne du paramètre stocké en mémoire tampon.  
  
## Syntaxe  
  
```  
  
      bool GetParamString(  
   DBORDINAL nParam,  
   CSimpleStringA& strOutput  
) throw( );  
bool GetParamString(  
   DBORDINAL nParam,  
   CSimpleStringW& strOutput  
) throw( );  
bool GetParamString(  
   DBORDINAL nParam,  
   CHAR* pBuffer,  
   size_t* pMaxLen  
) throw( );  
bool GetParamString(  
   DBORDINAL nParam,  
   WCHAR* pBuffer,  
   size_t* pMaxLen  
) throw( );  
```  
  
#### Paramètres  
 `nParam`  
 \[in\] Le nombre de paramètre \(décalage de 1\).  Le paramètre 0 est réservé pour les valeurs de retour.  Le numéro de paramètre représente l'index du paramètre en fonction de son ordre dans l'appel SQL ou celui d'une procédure stockée.  Consultez [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) pour obtenir un exemple.  
  
 `strOutput`  
 \[out\] données de chaîne ANSI \(**CSimpleStringA**\) ou Unicode \(**CSimpleStringW**\) du paramètre.  Vous devez passer un paramètre de type `CString`, par exemple :  
  
 [!code-cpp[NVC_OLEDB_Consumer#9](../../data/oledb/codesnippet/CPP/cdynamicparameteraccessor-getparamstring_1.cpp)]  
  
 `pBuffer`  
 \[out\] Un pointeur vers les données de chaîne ANSI \(**CHAR**\) ou Unicode \(**WCHAR**\) du paramètre.  
  
 `pMaxLen`  
 \[out\] Un pointeur à la taille de la mémoire tampon désignée par `pBuffer` \(en caractères, y compris la valeur de fin NULL\).  
  
## Notes  
 Retourne la valeur **vrai** en cas de réussite, ou **faux** en cas d'échec.  
  
 Si `pBuffer` est NULL, cette méthode fixera la taille de mémoire tampon requise dans la mémoire désignée par `pMaxLen` et renvoie **vrai** sans copier les données.  
  
 Cette méthode échoue si la mémoire tampon `pBuffer` n'est pas assez grande pour contenir la chaîne entière.  
  
 Utilisez `GetParamString` pour récupérer des données de paramètre de chaîne de la mémoire tampon.  Utilisez [GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) pour récupérer de la mémoire tampon des données de paramètre n'étant pas des chaînes de caractères.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDynamicParameterAccessor, classe](../../data/oledb/cdynamicparameteraccessor-class.md)