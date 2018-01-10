---
title: "Comment : utiliser la classe transformer dans un Pipeline de données | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- transformer class, example
- data pipelines, using transformer [Concurrency Runtime]
- using transformer in data pipelines [Concurrency Runtime]
ms.assetid: ca49cb3f-4dab-4b09-a9c9-d3a109ae4c29
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 76c8a50bd5a58d9fe6e4a68f05d9732e50fd04e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-transformer-in-a-data-pipeline"></a>Comment : utiliser la classe transformer dans un pipeline de données
Cette rubrique contient un exemple de base qui montre comment utiliser le [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) classe dans un pipeline de données. Pour obtenir un exemple plus complet qui utilise un pipeline de données pour effectuer le traitement d’image, consultez [procédure pas à pas : création d’un réseau de traitement d’Image](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).  
  
 *Traitement « pipeline » des données* est un modèle commun dans la programmation simultanée. Un pipeline de données se compose d’une série d’étapes, où chaque étape exécute une tâche et puis passe le résultat de ce travail à l’étape suivante. La `transformer` classe un rôle essentiel dans les données de pipelines car elle reçoit une valeur d’entrée, effectue le travail sur cette valeur, puis produit un résultat pour un autre composant à utiliser.  
  
## <a name="example"></a>Exemple  
 Cet exemple utilise le pipeline de données suivantes pour effectuer une série de transformations avec une valeur d’entrée initiale :  
  
1.  La première étape calcule la valeur absolue de son entrée.  
  
2.  La deuxième étape calcule la racine carrée de son entrée.  
  
3.  La troisième étape calcule le carré de son entrée.  
  
4.  La quatrième étape inverse son entrée.  
  
5.  La cinquième étape écrit le résultat final dans un tampon de messages.  
  
 Enfin, l’exemple imprime le résultat du pipeline sur la console.  
  
 [!code-cpp[concrt-data-pipeline#1](../../parallel/concrt/codesnippet/cpp/how-to-use-transformer-in-a-data-pipeline_1.cpp)]  
  
 Cet exemple génère la sortie suivante :  
  
```Output  
The result is -42.  
```  
  
 Il est courant pour une étape dans un pipeline de données pour générer une valeur dont le type diffère de sa valeur d’entrée. Dans cet exemple, la deuxième étape prend une valeur de type `int` comme entrée et produit la racine carrée de cette valeur (un `double`) comme sortie.  
  
> [!NOTE]
>  Dans cet exemple, le pipeline de données est à titre d’illustration. Étant donné que chaque opération de transformation effectue peu de travail, la surcharge requise pour effectuer la transmission de messages peut annuler les avantages de l’utilisation d’un pipeline de données.  
  
## <a name="compiling-the-code"></a>Compilation du code  
 Copiez l’exemple de code et collez-le dans un projet Visual Studio ou collez-le dans un fichier nommé `data-pipeline.cpp` , puis exécutez la commande suivante dans une fenêtre d’invite de commandes Visual Studio.  
  
 **CL.exe /EHsc data-pipeline.cpp**  
  
## <a name="see-also"></a>Voir aussi  
 [Bibliothèque d’agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md)   
 [Blocs de messages asynchrones](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Procédure pas à pas : création d’un réseau de traitement d’image](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)

