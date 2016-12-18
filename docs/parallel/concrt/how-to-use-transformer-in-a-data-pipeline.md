---
title: "Comment&#160;: utiliser la classe transformer dans un pipeline de donn&#233;es | Microsoft Docs"
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
  - "transformer, classe, exemple"
  - "pipelines de données, utiliser transformer [Runtime d’accès concurrentiel]"
  - "utiliser transformer dans des pipelines de données [Runtime d’accès concurrentiel]"
ms.assetid: ca49cb3f-4dab-4b09-a9c9-d3a109ae4c29
caps.latest.revision: 16
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: utiliser la classe transformer dans un pipeline de donn&#233;es
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique contient un exemple de base qui montre comment utiliser la classe [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) dans un pipeline de données.  Pour obtenir un exemple plus complet qui utilise un pipeline de données pour effectuer le traitement d'image, consultez [Procédure pas à pas : création d'un réseau de traitement d'image](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).  
  
 Le *traitement « pipeline » de données* est un modèle commun dans la programmation simultanée.  Un pipeline de données se compose d'une série d'étapes, où chaque étape exécute un travail puis passe le résultat de ce travail à l'étape suivante.  La classe `transformer` est un composant clé dans les pipelines de données car elle reçoit une valeur d'entrée, effectue un travail sur cette valeur, puis produit un résultat utilisable par un autre composant.  
  
## Exemple  
 Cet exemple utilise le pipeline de données suivant pour exécuter une série de transformations étant donné une valeur d'entrée initiale :  
  
1.  La première étape calcule la valeur absolue de son entrée.  
  
2.  La deuxième étape calcule la racine carrée de son entrée.  
  
3.  La troisième étape calcule le carré de son entrée.  
  
4.  La quatrième étape inverse son entrée.  
  
5.  La cinquième étape écrit le résultat final dans un tampon de messages.  
  
 Pour finir, l'exemple imprime le résultat du pipeline sur la console.  
  
 [!code-cpp[concrt-data-pipeline#1](../../parallel/concrt/codesnippet/CPP/how-to-use-transformer-in-a-data-pipeline_1.cpp)]  
  
 Cet exemple génère la sortie suivante :  
  
  **Le résultat est \-42.** Il est courant pour une étape dans un pipeline de données de générer une valeur dont le type diffère de sa valeur d'entrée.  Dans cet exemple, la deuxième étape prend une valeur de type `int` comme entrée et produit la racine carrée de cette valeur \( `double`\) comme sortie.  
  
> [!NOTE]
>  Le pipeline de données de cet exemple est fourni à titre d'illustration.  Étant donné que chaque opération de transformation effectue peu de travail, la surcharge requise pour effectuer le passage de message peut l'emporter sur les avantages que procure l'utilisation d'un pipeline de données.  
  
## Compilation du code  
 Copiez l'exemple de code et collez\-le dans un projet Visual Studio , ou collez\-le dans un fichier nommé `data-pipeline.cpp` puis exécutez la commande suivante dans une fenêtre d'invite de commandes Visual Studio.  
  
 **cl.exe \/EHsc data\-pipeline.cpp**  
  
## Voir aussi  
 [Bibliothèque d'agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md)   
 [Blocs de messages asynchrones](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Procédure pas à pas : création d'un réseau de traitement d'image](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)