---
title: Compilateur avertissement (niveau 1) C4182 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4182
dev_langs:
- C++
helpviewer_keywords:
- C4182
ms.assetid: 8970f3c6-e2dd-407e-b2ec-964360eb8b43
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
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 94e014a2eb65173e7022d7d247f073359f10587f
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4182"></a>Avertissement du compilateur (niveau 1) C4182
\#inclure au niveau d’imbrication est 'nombre' profondeur ; risque de récurrence infinie  
  
 Le compilateur a manqué d’espace sur le tas en raison du nombre de fichiers Include imbriqués. Un fichier Include est imbriqué quand il est inclus dans un autre fichier Include.  
  
 Ce message est une information et précède l’erreur [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md).
