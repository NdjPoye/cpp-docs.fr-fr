---
title: "Platform::WeakReference, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform::WeakReference"
ms.assetid: 8cfe1977-a8c7-4b7b-b539-25c77ed4c5f1
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::WeakReference, classe
Représente une référence faible à une instance d'une classe ref.  
  
## Syntaxe  
  
```vb  
class WeakReference  
```  
  
#### Paramètres  
  
## Membres  
  
### Constructeurs  
  
|Membre|Description|  
|------------|-----------------|  
|[WeakReference::WeakReference, constructeur](../cppcx/weakreference-weakreference-constructor-c-cx.md)|Initialise une nouvelle instance de la classe WeakReference.|  
  
### Méthodes  
  
|Membre|Description|  
|------------|-----------------|  
|[WeakReference::Resolve, méthode](../cppcx/weakreference-resolve-method-platform-namespace.md)|Retourne un handle vers la classe ref sous\-jacente, ou nullptr si l'objet n'existe plus.|  
  
### Opérateurs  
  
|Membre|Description|  
|------------|-----------------|  
|[WeakReference::operator\=](../cppcx/weakreference-operator-assign.md)|Assigne une nouvelle valeur à l'objet WeakReference.|  
  
## Notes  
 La classe WeakReference elle\-même n'est pas une classe ref et par conséquent elle n'hérite pas de Platform::Object^ et ne peut pas être utilisée dans la signature d'une méthode publique.  
  
## Voir aussi  
 [Espace de noms de plateforme](../cppcx/platform-namespace-c-cx.md)