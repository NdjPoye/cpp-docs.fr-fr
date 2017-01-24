---
title: "call_as | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.call_as"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "call_as attribute"
ms.assetid: a09d7f1f-353b-4870-9b45-f0284161695d
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# call_as
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Active une fonction de [local](../windows/local-cpp.md) à mapper à une fonction distante afin que lorsque la fonction distante est appelée, la fonction locale ne soit appelée.  
  
## Syntaxe  
  
```  
  
      [ call_as(  
   function  
) ]  
```  
  
#### Paramètres  
 *fonction*  
 La fonction locale qui doit être appelé lorsqu'une fonction distante est appelée.  
  
## Notes  
 L'attribut de **call\_as** C\+\+ a les mêmes fonctionnalités que l'attribut de [call\_as](http://msdn.microsoft.com/library/windows/desktop/aa366748) MIDL.  
  
## Exemple  
 Le code suivant montre comment vous pouvez utiliser **call\_as** pour mapper une fonction non \(**f1**\) à une fonction accessible à distance \(**Remf1**\) :  
  
```  
// cpp_attr_ref_call_as.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyLib")];  
[dual, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMInterface {  
   [local] HRESULT f1 ( int i );  
   [call_as(f1)] HRESULT Remf1 ( int i );   
};  
```  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|méthode d'interface|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [local](../windows/local-cpp.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)