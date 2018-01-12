---
title: Compilateur avertissement (niveau 1) C4951 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4951
dev_langs: C++
helpviewer_keywords: C4951
ms.assetid: 669d8bb7-5efa-4ba9-99db-4e65addbf054
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 199df135d5d2c00255037e5a1b31db80e2683d4f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4951"></a>Avertissement du compilateur (niveau 1) C4951
'function' a été modifié depuis que les données de profil ont été regroupées ; données de profil de fonction non utilisées  
  
 Une fonction d’un module d’entrée a été remplacée par [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), de sorte que les données de profil ne sont plus valides. Le module d’entrée a été recompilé après **/LTCG:PGINSTRUMENT** et a une fonction (***function***) avec un flux de contrôle différent de celui du module au moment de l’opération **/LTCG:PGINSTRUMENT** .  
  
 Cet avertissement est à caractère informatif. Pour résoudre cet avertissement, exécutez **/LTCG:PGINSTRUMENT**, relancez toutes les séries de tests, puis exécutez **/LTCG:PGOPTIMIZE**.  
  
 Si **/LTCG:PGOPTIMIZE** avait été utilisé, cet avertissement aurait été remplacé par une erreur.