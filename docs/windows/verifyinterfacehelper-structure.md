---
title: "VerifyInterfaceHelper, structure | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::VerifyInterfaceHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VerifyInterfaceHelper (structure)"
ms.assetid: ea95b641-199a-4fdf-964b-186b40cb3ba7
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# VerifyInterfaceHelper, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
template <  
   bool isWinRTInterface,  
   typename I  
>  
struct VerifyInterfaceHelper;  
  
template <  
   typename I  
>  
struct VerifyInterfaceHelper<false, I>;  
```  
  
#### Paramètres  
 `I`  
 Une interface à vérifier.  
  
 `isWinRTInterface`  
  
## Notes  
 Vérifie que l'interface spécifiée par le paramètre de modèle répond à certaines exigences.  
  
## Membres  
  
### Méthodes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[VerifyInterfaceHelper::Verify, méthode](../windows/verifyinterfacehelper-verify-method.md)||  
  
## Hiérarchie d'héritage  
 `VerifyInterfaceHelper`  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)