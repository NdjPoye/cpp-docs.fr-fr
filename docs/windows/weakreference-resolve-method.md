---
title: "WeakReference::Resolve, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::WeakReference::Resolve"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Resolve (méthode)"
ms.assetid: fc65a4b7-48a0-4d64-a793-37f566fdd8e7
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# WeakReference::Resolve, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
  
STDMETHOD(Resolve)  
   (REFIID riid,   
   _Deref_out_opt_ IInspectable **ppvObject  
);  
```  
  
#### Paramètres  
 `riid`  
 Un ID d'interface.  
  
 `ppvObject`  
 Lorsque cette opération se termine, une copie de la référence forte actuelle si le décompte de références fortes est différent de zéro.  
  
## Valeur de retour  
  
-   S\_OK si cette opération réussit et que le décompte de références fortes est à zéro.  Le paramètre `ppvObject` a la valeur `nullptr`.  
  
-   S\_OK si cette opération réussit et que le décompte de références fortes est différent de zéro.  Le paramètre `ppvObject` est affecté à la référence forte.  
  
-   Sinon, un HRESULT indiquant la raison de l'échec de cette opération.  
  
## Notes  
 Définit le pointeur spécifié vers la valeur de la référence forte actuelle si le décompte de références fortes est différent de zéro.  
  
## Configuration requise  
 **En\-tête :** implements.h  
  
 **Espace de noms :** Microsoft::WRL::Details  
  
## Voir aussi  
 [WeakReference, classe](../windows/weakreference-class1.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)