---
title: Compilateur avertissement (niveau 1) C4729 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4729
dev_langs: C++
helpviewer_keywords: C4729
ms.assetid: 36a0151f-f258-48d9-9444-ae6d41ff70a4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 57d6d5dc95ce3ef9cf4890b93ef1ab3abe2d6601
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4729"></a>Avertissement du compilateur (niveau 1) C4729
fonction trop importante pour les avertissements bas‚s sur les graphes de flux  
  
 Cet avertissement est généré quand une fonction est trop grande pour être compilée avec un contrôle fiable des situations qui génèrent un avertissement. Cet avertissement n’est généré que quand l’option du compilateur [/Od](../../build/reference/od-disable-debug.md) est utilisée.  
  
 Pour remédier à cet avertissement, fractionnez la fonction en fonctions plus petites.