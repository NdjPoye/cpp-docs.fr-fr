---
title: Compilateur avertissement (niveau 1) C4041 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4041
dev_langs:
- C++
helpviewer_keywords:
- C4041
ms.assetid: 107ee9fd-4b88-4f22-a18f-a20726831095
caps.latest.revision: 7
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
ms.openlocfilehash: f6578b938a5b8fcecd0bcb3f9a60134acaa30131
ms.contentlocale: fr-fr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4041"></a>Avertissement du compilateur (niveau 1) C4041
limite du compilateur : arrêt de la sortie de l’explorateur  
  
 Les informations du navigateur dépassent la limite du compilateur.  
  
 Cet avertissement peut être provoqué par la compilation avec [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) (informations du navigateur comprenant des variables locales).  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Pour résoudre ce problème, appliquez les solutions possibles suivantes.  
  
1.  Compilez avec /Fr (informations du navigateur sans variables locales).  
  
2.  Désactivez la sortie de navigateur (compilez sans /FR ou /Fr).
