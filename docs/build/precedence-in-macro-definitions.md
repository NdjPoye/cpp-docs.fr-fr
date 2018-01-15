---
title: "Priorité dans les définitions de Macro | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, precedence in macro definitions
- macros, precedence
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7421ef51c37e3724bdb986321581e6736a62e18b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="precedence-in-macro-definitions"></a>Priorité dans les définitions de macros
Si une macro possède plusieurs définitions, NMAKE utilise la définition de la priorité la plus élevée. La liste suivante indique l’ordre de priorité, du plus élevé au plus bas :  
  
1.  Une macro définie sur la ligne de commande  
  
2.  Une macro définie dans un makefile ou le fichier include  
  
3.  Une macro héritée de la variable d’environnement  
  
4.  Une macro définie dans le fichier Tools.ini  
  
5.  Une macro prédéfinie, tel que [CC](../build/command-macros-and-options-macros.md) et [AS](../build/command-macros-and-options-macros.md)  
  
 Utilisez /E pour que les macros héritées de variables d’environnement substituent les macros du makefile portant le même nom. Utilisez **! UNDEF** pour remplacer une ligne de commande.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition d’une macro NMAKE](../build/defining-an-nmake-macro.md)