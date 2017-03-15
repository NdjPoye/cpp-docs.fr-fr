---
title: "lcid | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.lcid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LCID attribute"
ms.assetid: 7f248c69-ee1c-42c3-9411-39cf27c9f43d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# lcid
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous permet de passer un identificateur de paramètres régionaux à une fonction.  
  
## Syntaxe  
  
```  
  
[lcid]  
  
```  
  
## Notes  
 L'attribut de **LCID** C\+\+ implémente les fonctionnalités de l'attribut de [LCID](http://msdn.microsoft.com/library/windows/desktop/aa367067) MIDL.  si vous souhaitez implémenter des paramètres régionaux pour un bloc bibliothèque, utilisez le paramètre de **lcid\=**`lcid` à l'attribut de [module](../windows/module-cpp.md) .  
  
## Exemple  
  
```  
// cpp_attr_ref_lcid.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLibrary")];  
typedef long HRESULT;  
  
[dual, uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA")]  
__interface IStatic {  
   HRESULT MyFunc([in, lcid] long LocaleID, [out, retval] BSTR * ReturnVal);  
};  
```  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|paramètre d'interface|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)