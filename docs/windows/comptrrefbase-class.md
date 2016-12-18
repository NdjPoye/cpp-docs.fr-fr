---
title: "ComPtrRefBase, classe | Microsoft Docs"
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
  - "client/Microsoft::WRL::Details::ComPtrRefBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ComPtrRefBase (classe)"
ms.assetid: 6d344c1a-cc13-4a3f-8a0d-f167ccb9348f
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtrRefBase, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
template <  
   typename T  
>  
class ComPtrRefBase;  
```  
  
#### Paramètres  
 `T`  
 Un type [CoomPtr\<T\>](../windows/comptr-class.md) ou un type dérivé de celui\-ci, pas seulement l'interface représentée par le ComPtr.  
  
## Notes  
 Représente la classe de base pour la classe [ComPtrRef](../windows/comptrref-class.md).  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`InterfaceType`|Un synonyme du type de paramètre de modèle `T`.|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[ComPtrRefBase::operator IInspectable\*\*, opérateur](../windows/comptrrefbase-operator-iinspectable-star-star-operator.md)|Caste la donnée membre [ptr\_](../windows/comptrrefbase-ptr-data-member.md) actuelle en un pointeur\-vers\-un\-pointeur vers l'interface IInspectable.|  
|[ComPtrRefBase::operator IUnknown\*\*, opérateur](../windows/comptrrefbase-operator-iunknown-star-star-operator.md)|Caste la donnée membre [ptr\_](../windows/comptrrefbase-ptr-data-member.md) actuelle en un pointeur\-vers\-un\-pointeur vers l'interface IUnknown.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[ComPtrRefBase::ptr\_, données de membre](../windows/comptrrefbase-ptr-data-member.md)|Pointeur vers le type spécifié par le nom du paramètre de modèle actuel.|  
  
## Hiérarchie d'héritage  
 `ComPtrRefBase`  
  
## Configuration requise  
 **En\-tête :** client.h  
  
 **Espace de noms :** Microsoft::WRL::Details  
  
## Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)