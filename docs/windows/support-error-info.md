---
title: "support_error_info | Microsoft Docs"
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
  - "vc-attr.support_error_info"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "support_error_info (attribut)"
ms.assetid: 20a2b55c-4738-4b35-a71d-e5e9c3a7e3bc
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# support_error_info
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Implémente la prise en charge du retour d’erreurs détaillées.  
  
## Syntaxe  
  
```  
  
[ support_error_info(  
   error_interface=  
uuid  
) ]  
  
```  
  
#### Paramètres  
 **error\_interface**  
 Identificateur de l’interface qui implémente **IErrorInfo**.  
  
## Notes  
 L’attribut C\+\+ **support\_error\_info** implémente la prise en charge permettant de retourner au client les erreurs détaillées et contextuelles rencontrées par l’objet cible. Pour que l’objet prenne en charge les erreurs, les méthodes de l’interface **IErrorInfo** doivent être implémentées par l’objet. Pour plus d’informations, consultez [Prise en charge d’IDispatch et IErrorInfo](../atl/supporting-idispatch-and-ierrorinfo.md).  
  
 Cet attribut ajoute la classe [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) comme classe de base à l’objet cible. Il en résulte une implémentation par défaut de **ISupportErrorInfo** qui peut être utilisée quand une seule interface génère des erreurs sur un objet.  
  
## Exemple  
 Le code suivant ajoute la prise en charge par défaut de l’interface **ISupportErrorInfo** à l’objet `CMyClass`.  
  
```  
// cpp_attr_ref_support_error_info.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="mymod")];  
[object, uuid("f0b17d66-dc6e-4662-baaf-76758e09c878")]  
__interface IMyErrors  
{  
};  
  
[ coclass, support_error_info("IMyErrors"),  
  uuid("854dd392-bdc7-4781-8667-8757936f2a4f") ]  
class CMyClass  
{  
};  
```  
  
## Configuration requise  
  
### Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**classe**|  
|**Renouvelable**|Oui|  
|**Attributs requis**|Aucun|  
|**Attributs non valides**|None|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [COM Attributes](../windows/com-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)