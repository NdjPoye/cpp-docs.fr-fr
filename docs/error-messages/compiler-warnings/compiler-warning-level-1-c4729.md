---
title: Compilateur avertissement (niveau 1) C4729 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4729
dev_langs:
- C++
helpviewer_keywords:
- C4729
ms.assetid: 36a0151f-f258-48d9-9444-ae6d41ff70a4
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
ms.openlocfilehash: 57a83903ac31b7f05ee1892cca011c9ef9d8fe74
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4729"></a>Avertissement du compilateur (niveau 1) C4729
fonction trop importante pour les avertissements bas‚s sur les graphes de flux  
  
 Cet avertissement est généré quand une fonction est trop grande pour être compilée avec un contrôle fiable des situations qui génèrent un avertissement. Cet avertissement est uniquement généré lorsque la [/Od](../../build/reference/od-disable-debug.md) option du compilateur utilisée.  
  
 Pour remédier à cet avertissement, fractionnez la fonction en fonctions plus petites.
