---
title: "Platform::CallbackContext (&#233;num&#233;ration) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::CallbackContext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::CallbackContext (énumération)"
ms.assetid: 60e0c7cb-5d8f-482a-bdca-ca9335ae4899
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 3
---
# Platform::CallbackContext (&#233;num&#233;ration)
Spécifie le contexte de thread dans lequel s’exécute une fonction de rappel \(Gestionnaire d’événements\).  
  
## Syntaxe  
  
```cpp  
enum class CallbackContext {};  
```  
  
## Membres  
  
|Code de type|Description|  
|------------------|-----------------|  
|Any|La fonction de rappel peut s’exécuter sur n’importe quel contexte de thread.|  
|Identique|La fonction de rappel peut s’exécuter uniquement sur le contexte de thread qui a démarré l’opération asynchrone.|  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **Métadonnées :** platform.winmd