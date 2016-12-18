---
title: "WeakReference, classe | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::WeakReference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WeakReference (classe)"
ms.assetid: 3f4c956b-dbbd-49b1-8cfa-9509a9956c97
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# WeakReference, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
class WeakReference;  
```  
  
## Remarques  
 Représente une *référence faible* pouvant être utilisée avec les le runtime Windows ou le COM classique.  Une référence faible représente un objet qui peut être accessible ou non.  
  
 Un objet `WeakReference` conserve une *référence forte*, qui est un pointeur vers un objet, et un*décompte de références fortes*, qui est le nombre de copies de la référence forte qui ont été distribuées par la méthode Resolve\(\).  Lorsque le décompte de références fortes est différent de zéro, la référence forte est valide et l'objet est accessible.  Lorsque le décompte de références fortes devient nul, la référence forte n'est pas valide et l'objet est inaccessible.  
  
 Un objet WeakReference est généralement utilisé pour représenter un objet dont l'existence est contrôlée par un thread ou une application externe.  Par exemple, construisez un objet WeakReference à partir d'une référence à un fichier objet.  Lorsque le fichier est ouvert, la référence forte est valide.  Mais si le fichier est fermé, la référence forte devient non valide.  
  
 Les méthodes de WeakReference sont thread\-safe.  
  
## Membres  
  
### Constructeurs publics  
  
|Name|Description|  
|----------|-----------------|  
|[WeakReference::WeakReference, constructeur](../windows/weakreference-weakreference-constructor.md)|Initialise une nouvelle instance de la classe WeakReference.|  
|[WeakReference::~WeakReference, destructeur](../windows/weakreference-tilde-weakreference-destructor.md)|Libère \(détruit\) l'instance actuelle de la classe WeakReference.|  
  
### Méthodes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[WeakReference::DecrementStrongReference, méthode](../windows/weakreference-decrementstrongreference-method.md)|Décrémente le décompte de références fortes de l'objet WeakReference actuel.|  
|[WeakReference::IncrementStrongReference, méthode](../windows/weakreference-incrementstrongreference-method.md)|Incrémente le décompte de références fortes de l'objet WeakReference actuel.|  
|[WeakReference::Resolve, méthode](../windows/weakreference-resolve-method.md)|Définit le pointeur spécifié vers la valeur de la référence forte actuelle si le décompte de références fortes est différent de zéro.|  
|[WeakReference::SetUnknown, méthode](../windows/weakreference-setunknown-method.md)|Définit la référence forte de l'objet WeakReference actuel au pointeur de l'interface spécifiée.|  
  
## Hiérarchie d'héritage  
 `WeakReference`  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)