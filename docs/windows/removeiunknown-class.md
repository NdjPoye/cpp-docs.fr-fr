---
title: "RemoveIUnknown, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::Details::RemoveIUnknown"
dev_langs: 
  - "C++"
ms.assetid: 998e711a-7d1a-44c6-a016-e6167aa40863
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# RemoveIUnknown, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
template <  
   typename T  
>  
struct RemoveIUnknown;  
  
template <  
   typename T  
>  
class RemoveIUnknown : public T;  
```  
  
#### Paramètres  
 `T`  
 Une classe.  
  
## Remarques  
 Crée un type équivalent à un type basé sur `IUnknown`, mais ayant des fonctions membres `QueryInterface`, `AddRef` et `Release` non virtuelles.  
  
 Par défaut, les méthodes COM fournissent des méthodes `QueryInterface`, `AddRef`, et Release virtuelles.  Toutefois, `ComPtr` ne requiert pas la surcharge des méthodes virtuelles.  `RemoveIUnknown` élimine cette surcharge en fournissant des méthodes `QueryInterface`, `AddRef`, et `Release` privées et non virtuelles.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`ReturnType`|Un synonyme d'un type équivalent au paramètre de modèle `T` mais possédant des membres d'IUnknown non virtuels.|  
  
## Hiérarchie d'héritage  
 `T`  
  
 `RemoveIUnknown`  
  
## Configuration requise  
 **En\-tête :** client.h  
  
 **Espace de noms :** Microsoft::WRL::Details  
  
## Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)