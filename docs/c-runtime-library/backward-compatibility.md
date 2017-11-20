---
title: "Compatibilité descendante | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.programs
dev_langs: C++
helpviewer_keywords:
- CRT, compatibility
- backward compatibility, C run-time libraries
- compatibility, C run-time libraries
- backward compatibility
ms.assetid: cc3175cf-97fd-492f-b329-5791aea63090
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 341dc7f2b16449356fab60f79424f5031ceefd6d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="backward-compatibility"></a>Compatibilité descendante
Pour la compatibilité entre les versions de produit, la bibliothèque OLDNAMES.LIB mappe les anciens noms sur les nouveaux. Par exemple, `open` est mappé sur `_open`. Vous devez lier explicitement avec OLDNAMES.LIB uniquement lorsque vous compilez avec les combinaisons d’options de ligne de commande suivantes :  
  
-   `/Zl` (omettez le nom de la bibliothèque par défaut dans le fichier objet) et `/Ze` (par défaut - utilisez les extensions Microsoft)  
  
-   `/link` (contrôle d’éditeur de lien), `/NOD` (pas de recherche dans la bibliothèque par défaut) et `/Ze`  
  
 Pour plus d’informations sur les options de ligne de commande du compilateur, consultez l’article [Référence du compilateur](../build/reference/compiler-options.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Compatibilité](../c-runtime-library/compatibility.md)