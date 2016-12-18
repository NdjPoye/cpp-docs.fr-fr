---
title: "Creating Registrar Scripts | Microsoft Docs"
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
  - "ATL, Registre"
  - "registrar scripts [ATL]"
  - "scripts, registry scripting"
  - "scripts, créer"
  - "scripts, Registrar scripts"
ms.assetid: cbd5024b-8061-4a71-be65-7fee90374a35
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating Registrar Scripts
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un script d'inscription fournit piloté par des données, plutôt que motivé par l'API, l'accès à la base de registres.  L'accès piloté par des données est en général plus efficace parce qu'il prend uniquement un ou deux lignes un script pour ajouter une clé au Registre.  
  
 [L'Assistant Contrôle ATL](../atl/reference/atl-control-wizard.md) génère automatiquement un script d'inscription de votre serveur COM.  Vous pouvez rechercher ce script dans le fichier .rgs associé à votre objet.  
  
 Le moteur de script ATL Registrar traite votre script d'inscription au moment de l'exécution.  ATL appelle automatiquement le moteur de script pendant l'installation de serveur.  
  
 Cet article décrit les rubriques suivantes liés aux scripts d'inscription :  
  
-   [Syntaxe de fonctionnement de \(BNF\) de formulaire de Backus Nauer](../atl/understanding-backus-nauer-form-bnf-syntax.md)  
  
-   [La compréhension analysent les arborescences](../atl/understanding-parse-trees.md)  
  
-   [Exemples de script de Registre](../atl/registry-scripting-examples.md)  
  
-   [Utilisation de paramètres remplaçables \(le préprocesseur du registre\)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)  
  
-   [Appeler des scripts](../atl/invoking-scripts.md)  
  
## Voir aussi  
 [Composant de registre \(Inscription\)](../atl/atl-registry-component-registrar.md)