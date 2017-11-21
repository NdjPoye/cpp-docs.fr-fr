---
title: "Alternatives d’entrée-sortie | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: I/O [C++], alternatives
ms.assetid: 9f8401c7-d90d-4285-8918-63573df74a80
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: edf17c4524fd42fd0db327aca9de85e9d63eb651
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="inputoutput-alternatives"></a>Alternatives d'entrée/sortie
Visual C++ propose plusieurs alternatives pour la programmation d’E/S :  
  
-   E/S directe et sans mise en mémoire tampon avec bibliothèque Runtime C  
  
-   E/S de flux de bibliothèque Runtime C ANSI  
  
-   E/S directe de console et port  
  
-   Bibliothèque MFC (Microsoft Foundation Class)  
  
-   Bibliothèque standard C++ Microsoft  
  
 Les classes iostream sont utiles pour les E/S de texte mis en forme mises en mémoire tampon. Elles sont également utiles pour les E/S binaires ou sans mise en mémoire tampon si vous avez besoin d’une interface de programmation C++ et que vous décidez de ne pas utiliser la bibliothèque MFC. Les classes iostream sont une alternative d’E/S orientée objet aux fonctions Runtime C.  
  
 Vous pouvez utiliser les classes iostream avec le système d’exploitation Microsoft Windows. Les flux de chaîne et de fichier fonctionnent sans restrictions, mais les objets de flux en mode caractère `cin`, `cout`, `cerr` et `clog` ne sont pas cohérents avec l’interface graphique utilisateur Windows. Vous pouvez également dériver des classes de flux personnalisées qui interagissent directement avec l’environnement Windows.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition d’un flux](../standard-library/what-a-stream-is.md)

