---
title: Compilateur avertissement (niveau 4) C4710 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4710
dev_langs: C++
helpviewer_keywords: C4710
ms.assetid: 76381ec7-3fc1-4bee-9a0a-c2c8307b92e2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e0464d924c21a029a97a8f03d30f88127f3aea6a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4710"></a>Avertissement du compilateur (niveau 4) C4710
'fonction' : fonction non inline  
  
 La fonction donnée a été sélectionnée pour expansion inline, mais le compilateur n’a pas effectué l’incorporation (inlining).  
  
 La fonctionnalité inline est effectuée à la discrétion du compilateur. Le **inline** (mot clé), comme le **inscrire** (mot clé), est utilisé comme un indicateur pour le compilateur. Le compilateur utilise l’heuristique pour déterminer s’il doit incorporer une fonction particulière pour accélérer le code lors de la compilation pour la vitesse, ou s’il doit incorporer une fonction particulière pour rendre le code plus petit lors de la compilation pour l’espace. Le compilateur seront les très petites fonctions inline uniquement lors de la compilation pour l’espace.  
  
 Dans certains cas, le compilateur n’incorpore pas une fonction particulière pour des raisons mécaniques. Consultez [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md) pour obtenir la liste des raisons, le compilateur peut ne pas incorporer une fonction.  
  
 Cet avertissement est désactivé par défaut. Consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md) pour plus d'informations.