---
title: Compilateur avertissement (niveau 1) C4650 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4650
dev_langs: C++
helpviewer_keywords: C4650
ms.assetid: 3190b3e3-dcd6-4846-939b-f900ab652b2a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: af10d05562c0c60c6a010e105441533362d058df
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4650"></a>Avertissement du compilateur (niveau 1) C4650
informations de débogage pas dans l’en-tête précompilé ; Seuls les symboles globaux de l’en-tête seront disponibles  
  
 Le fichier d’en-tête précompilé n’a pas été compilé avec les informations de débogage symboliques à Microsoft.  
  
 Lorsque lié, le fichier exécutable ou DLL de bibliothèque résultant n’inclura pas les informations de débogage pour les symboles locaux contenus dans l’en-tête précompilé.  
  
 Cet avertissement peut être évité en recompilant le fichier d’en-tête précompilé avec le [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) option de ligne de commande.