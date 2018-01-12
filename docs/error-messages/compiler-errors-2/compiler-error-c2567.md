---
title: Erreur du compilateur C2567 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2567
dev_langs: C++
helpviewer_keywords: C2567
ms.assetid: 9c140ac9-7059-47e6-9ba1-e7939c8c0dc3
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 28cd1dc74e15ae3cd63286fc6de9c3508bb1d279
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2567"></a>Erreur du compilateur C2567
Impossible d’ouvrir les métadonnées dans 'fichier', fichier peut avoir été supprimé ou déplacé  
  
 Un fichier de métadonnées a été référencé dans la source (avec `#using`) est introuvable dans le même répertoire par le processus de back-end du compilateur tel qu’il était par le processus de front-end du compilateur. Consultez [#using, Directive](../../preprocessor/hash-using-directive-cpp.md) pour plus d’informations.  
  
 C2567 peut être générée si vous compilez avec **/c** sur un ordinateur, puis tentez une génération de code de l’édition de liens sur un autre ordinateur. Pour plus d’informations, consultez [/LTCG (génération de Code d’édition de liens)](../../build/reference/ltcg-link-time-code-generation.md)).  
  
 Il peut également indiquer que votre ordinateur n’avait aucun plus de mémoire.  
  
 Pour corriger cette erreur, assurez-vous que le fichier de métadonnées est dans le même emplacement de répertoire pour toutes les phases du processus de génération.