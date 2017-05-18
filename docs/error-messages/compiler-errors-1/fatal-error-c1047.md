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
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: bee5dd89bf6ef92445466b12d79be5ba39d9cb5b
ms.contentlocale: fr-fr
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1047"></a>Erreur irrécupérable C1047
Le fichier objet ou le fichier bibliothèque 'fichier' a été créé à l’aide d’un compilateur antérieur à celui d’autres objets ; régénérez les objets et bibliothèques obsolètes  
  
 L’erreur C1047 se produit quand des fichiers objets ou des bibliothèques générés à l’aide de la commande **/LTCG** sont liés entre eux, alors qu’ils ont été créés avec des versions différentes de l’ensemble d’outils Visual C++.  
  
 Cela peut se produire si vous commencez à utiliser une nouvelle version du compilateur sans avoir effectué de régénération propre des fichiers objets ou des bibliothèques existants.  
  
 Pour résoudre l’erreur C1047, régénérez tous les fichiers objets et bibliothèques.
