---
title: "Erreur irrécupérable C1047 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C1047
dev_langs: C++
helpviewer_keywords: C1047
ms.assetid: e1bbbc6b-a5bc-4c23-8203-488120a0ec78
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6ddc117d1e83c635bfbc644606c6c8c6032ff4f8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1047"></a>Erreur irrécupérable C1047
Le fichier objet ou le fichier bibliothèque 'fichier' a été créé à l’aide d’un compilateur antérieur à celui d’autres objets ; régénérez les objets et bibliothèques obsolètes  
  
 L’erreur C1047 se produit quand des fichiers objets ou des bibliothèques générés à l’aide de la commande **/LTCG** sont liés entre eux, alors qu’ils ont été créés avec des versions différentes de l’ensemble d’outils Visual C++.  
  
 Cela peut se produire si vous commencez à utiliser une nouvelle version du compilateur sans avoir effectué de régénération propre des fichiers objets ou des bibliothèques existants.  
  
 Pour résoudre l’erreur C1047, régénérez tous les fichiers objets et bibliothèques.