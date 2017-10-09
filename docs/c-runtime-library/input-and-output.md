---
title: "Entrée et sortie | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.io
dev_langs:
- C++
helpviewer_keywords:
- input routines
- I/O [CRT]
- I/O routines
- I/O [CRT], routines
- output routines
ms.assetid: 1c177301-e341-4ca0-aedc-0a87fe1c75ae
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 5c4705ae56f11c1299e512814f8d83a49690a6ac
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="input-and-output"></a>Entrées et sorties
Les fonctions d’E/S, lisent et écrivent des données de et vers des fichiers et appareils. Les opérations d’E/S sur les fichiers ont lieu en mode texte ou binaire. La bibliothèque Runtime Microsoft propose trois types de fonctions d’E/S :  
  
-   Les fonctions [d’E/S de flux](../c-runtime-library/stream-i-o.md) traitent les données en tant que flux de caractères individuels.  
  
-   Les fonctions [d’E/S de bas niveau](../c-runtime-library/low-level-i-o.md) appellent le système d’exploitation directement pour l’opération du niveau inférieur à celui fourni par les E/S de flux.  
  
-   Les fonctions [d’E/S de console et de port](../c-runtime-library/console-and-port-i-o.md) lisent ou écrivent directement dans une console (clavier et écran) ou un port d’E/S (par exemple un port d’imprimante).  
  
    > [!NOTE]
    >  Étant donné que les fonctions de flux de données sont mises en mémoire tampon et que les fonctions de bas niveau ne le sont pas, ces deux types de fonctions sont généralement incompatibles. Pour traiter un fichier particulier, utilisez exclusivement des fonctions de flux ou de bas niveau.  
  
## <a name="see-also"></a>Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)
