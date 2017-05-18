---
title: Compilateur avertissement (niveau 1) C4953 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4953
dev_langs:
- C++
helpviewer_keywords:
- C4953
ms.assetid: 3c4f6ac6-3976-41ab-8a27-3c41d7472ea7
caps.latest.revision: 8
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
ms.openlocfilehash: d0b8ba97d493cb6e840be1023f7c6bd29a5cbd1a
ms.contentlocale: fr-fr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4953"></a>Avertissement du compilateur (niveau 1) C4953
'function' Inline a été modifié depuis le rassemblement des données de profil ; données de profil non utilisées  
  
 Lorsque vous utilisez [/LTCG : PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), le compilateur a détecté un module d’entrée qui a été recompilé après `/LTCG:PGINSTRUMENT` et possède une fonction (***fonction***) qui a été modifiée et où les séries de tests existantes ont identifié la fonction comme un candidat pour incorporation (inlining). Toutefois, en raison de la recompilation du module, la fonction ne sera plus candidate à l’incorporation (inlining).  
  
 Cet avertissement possède un caractère informatif. Pour résoudre cet avertissement, exécutez `/LTCG:PGINSTRUMENT`, relancez toutes les séries de tests, puis exécutez `/LTCG:PGOPTIMIZE`.  
  
 Si `/LTCG:PGOPTIMIZE` avait été utilisé, cet avertissement aurait été remplacé par une erreur.
