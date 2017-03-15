---
title: "Comment&#160;: g&#233;n&#233;rer des composants COM sans inscription | Microsoft Docs"
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
  - "composants COM, sans inscription"
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Comment&#160;: g&#233;n&#233;rer des composants COM sans inscription
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les composants COM sans inscription sont des composants COM qui ont des manifestes générés dans les DLL.  
  
### Pour générer des manifestes dans les composants COM  
  
1.  Ouvrez les pages des propriétés de projet pour le composant COM.  
  
2.  Développez le nœud **Propriétés de configuration**, puis développez le nœud **Outil Manifeste**.  
  
3.  Sélectionnez la page de propriétés **Entrée et sortie**, puis définissez la propriété **Incorporer le manifeste** à **Oui**.  
  
4.  Cliquez sur **OK**.  
  
5.  Générez la solution.  
  
## Voir aussi  
 [Applications isolées](http://msdn.microsoft.com/library/aa375190)   
 [Assemblys côte à côte](_win32_side_by_side_assemblies)   
 [Comment : générer des applications isolées pour consommer des composants COM](../build/how-to-build-isolated-applications-to-consume-com-components.md)