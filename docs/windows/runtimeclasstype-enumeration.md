---
title: "RuntimeClassType, &#233;num&#233;ration | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::RuntimeClassType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RuntimeClassType (énumération)"
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RuntimeClassType, &#233;num&#233;ration
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie le type d'instance [RuntimeClass](../windows/runtimeclass-class.md) prise en charge.  
  
## Syntaxe  
  
```  
enum RuntimeClassType;  
```  
  
## Membres  
  
### Valeurs  
  
|Nom|Description|  
|---------|-----------------|  
|`ClassicCom`|Une classe d'exécution COM classique.|  
|`Delegate`|Équivalent à **ClassicCom**.|  
|`InhibitFtmBase`|Désactive la prise en charge de `FtmBase` tandis que `__WRL_CONFIGURATION_LEGACY__` n'est pas défini.|  
|`InhibitWeakReference`|Désactive la prise en charge de références faibles.|  
|`WinRt`|Classe [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].|  
|`WinRtClassicComMix`|Combinaison de `WinRt` et de `ClassicCom`.|  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL, espace de noms  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)