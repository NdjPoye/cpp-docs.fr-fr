---
title: "Running the Program as a Local Server | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL (services), running as local servers"
  - "déboguer (ATL), running services as local server"
ms.assetid: eb9701e6-e2a8-4666-897f-0c893aec8ac7
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Running the Program as a Local Server
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si exécuter le programme en tant que service est gênante, vous pouvez temporairement modifier le Registre afin que le programme est lancé comme un serveur local normal.  Renommez simplement la valeur d' `LocalService` sous votre AppID à `_LocalService` et assurez \-vous que la clé d' `LocalServer32` sous le CLSID est configuré correctement.  \(Notez que l'utilisation DCOMCNFG spécifier que votre application doit être exécutée sur un autre ordinateur renomme votre clé de `LocalServer32` à `_LocalServer32`.\) L'exécution de votre programme en tant que serveur local prend quelques plus de secondes au démarrage car l'appel à **StartServiceCtrlDispatcher** dans `CAtlServiceModuleT::Start` prend quelques secondes avant qu'il échoue.  
  
## Voir aussi  
 [Debugging Tips](../atl/debugging-tips.md)