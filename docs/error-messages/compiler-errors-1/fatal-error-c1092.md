---
title: "Erreur irr&#233;cup&#233;rable C1092 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1092"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1092"
ms.assetid: bcaa87f0-fbfc-4a33-844b-3b9f5d67f279
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable C1092
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Modifier & Continuer ne prend pas en charge les modifications sur les types de données ; génération requise  
  
 Vous avez modifié ou ajouté un type de données depuis la dernière génération réussie.  
  
-   Modifier & Continuer ne prend pas en charge les modifications sur les types de données existants, y compris les définitions de styles class, struct ou enum.  Vous devez arrêter le débogage et régénérer l'application.  
  
-   Modifier & Continuer ne prend pas en charge l'addition de types de données si un fichier de base de données du programme, tel que vc*x*0.pdb \(où *x* est le numéro de version principale de Visual C\+\+ utilisé\) est en lecture seule.  Pour ajouter des types de données, le compilateur doit ouvrir le fichier .pdb en mode écriture.  
  
### Pour supprimer cette erreur sans mettre fin à la session de débogage en cours  
  
1.  Replacez le type de données dans l'état où il se trouvait avant l'erreur.  
  
2.  Dans le menu **Déboguer**, choisissez **Appliquer les modifications du code**.  
  
### Pour supprimer cette erreur sans modifier votre code source  
  
1.  Dans le menu **Déboguer**, choisissez **Arrêter le débogage**.  
  
2.  Dans le menu **Générer**, cliquez sur **Générer**.  
  
 Pour plus d'informations, consultez [Modifications de code prises en charge](../Topic/Supported%20Code%20Changes%20\(C++\).md).