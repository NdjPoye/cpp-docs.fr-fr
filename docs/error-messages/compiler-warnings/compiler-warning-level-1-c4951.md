---
title: Compilateur avertissement (niveau 1) C4951 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4951
dev_langs:
- C++
helpviewer_keywords:
- C4951
ms.assetid: 669d8bb7-5efa-4ba9-99db-4e65addbf054
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
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: da1b8904a6daf8e356cf65bb80f0fd36f467a35f
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4951"></a>Avertissement du compilateur (niveau 1) C4951
'function' a été modifié depuis que les données de profil ont été regroupées ; données de profil de fonction non utilisées  
  
 Une fonction a été modifiée dans un module d’entrée [/LTCG : PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), de sorte que les données de profil ne sont plus valides. Le module d’entrée a été recompilé après **/LTCG:PGINSTRUMENT** et a une fonction (***function***) avec un flux de contrôle différent de celui du module au moment de l’opération **/LTCG:PGINSTRUMENT** .  
  
 Cet avertissement est à caractère informatif. Pour résoudre cet avertissement, exécutez **/LTCG:PGINSTRUMENT**, relancez toutes les séries de tests, puis exécutez **/LTCG:PGOPTIMIZE**.  
  
 Si **/LTCG:PGOPTIMIZE** avait été utilisé, cet avertissement aurait été remplacé par une erreur.
