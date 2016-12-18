---
title: "At least one configuration was not loaded because it does not have a configuration name attribute | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.projfile_nameless_config"
ms.assetid: 711f7253-308b-44e0-b8bc-ca5c16536a2c
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# At least one configuration was not loaded because it does not have a configuration name attribute
Chaque section `<Config>` d'un fichier .csproj ou .vbproj doit avoir un attribut Name qui définit un nom unique pour cette configuration.  Ce diagnostic indique que l'attribut Name est manquant.  Si l'attribut Name ne figure pas dans une configuration, cette configuration ne sera pas chargée dans le projet.  
  
 La cause la plus probable de cette erreur est la modification manuelle du fichier projet.  
  
 **Pour corriger cette erreur**  
  
-   Insérez un nom de configuration juste après la ligne `<Config>`  dans le fichier projet.  
  
    ```  
    Name = "someconfigname"  
    ```  
  
     `Debug`  et  `Release` sont deux noms de configurations types.  
  
## Voir aussi  
 [Fichiers projet](../ide/project-files.md)   
 [NIB: Project Properties \(Visual Studio\)](http://msdn.microsoft.com/fr-fr/eb4c97ed-f667-4850-98d0-6e2a4d21bbca)