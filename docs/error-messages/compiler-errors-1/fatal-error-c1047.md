---
title: "Erreur irrécupérable C1047 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1047
dev_langs:
- C++
helpviewer_keywords:
- C1047
ms.assetid: e1bbbc6b-a5bc-4c23-8203-488120a0ec78
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b848f874f382e3d4f944a7eb372db9dcc5011f59
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1047"></a>Erreur irrécupérable C1047
Le fichier objet ou le fichier bibliothèque 'fichier' a été créé à l’aide d’un compilateur antérieur à celui d’autres objets ; régénérez les objets et bibliothèques obsolètes  
  
 L’erreur C1047 se produit quand des fichiers objets ou des bibliothèques générés à l’aide de la commande **/LTCG** sont liés entre eux, alors qu’ils ont été créés avec des versions différentes de l’ensemble d’outils Visual C++.  
  
 Cela peut se produire si vous commencez à utiliser une nouvelle version du compilateur sans avoir effectué de régénération propre des fichiers objets ou des bibliothèques existants.  
  
 Pour résoudre l’erreur C1047, régénérez tous les fichiers objets et bibliothèques.
