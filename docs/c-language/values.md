---
title: Valeurs | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 24003f89-220f-4f93-be7a-b650c26157d7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ea979083fb00d57e455b97c2f6b94f7ea7c6b596
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="values"></a>Valeurs
**ANSI 3.1.2.5** Représentations et jeux de valeurs des différents types de nombres à virgule flottante  
  
 Le type **float** contient 32 bits : 1 pour le signe, 8 pour l’exposant et 23 pour la mantisse. Sa plage est +/- 3.4E38 avec au moins 7 chiffres de précision.  
  
 Le type **double** contient 64 bits : 1 pour le signe, 11 pour l’exposant et 52 pour la mantisse. Sa plage est +/- 1.7E308 avec au moins 15 chiffres de précision.  
  
 Le type **long double** contient 80 bits : 1 pour le signe, 15 pour l’exposant et 64 pour la mantisse. Sa plage est +/- 1.2E4932 avec au moins 19 chiffres de précision. Notez qu’avec le compilateur Microsoft C, la représentation du type **long double** est identique au type **double**.  
  
## <a name="see-also"></a>Voir aussi  
 [Mathématiques à virgule flottante](../c-language/floating-point-math.md)