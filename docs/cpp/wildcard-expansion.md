---
title: "Développement des caractères génériques | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _setargv
dev_langs: C++
helpviewer_keywords:
- asterisk wildcard
- _setargv function
- command line [C++], processing arguments
- command line [C++], wildcards
- command-line wildcards
- question mark, wildcard
ms.assetid: 1a543398-607b-4404-93d1-45d290bde638
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2c9bbb5dcc706e08b2b985769248969f9bd23201
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="wildcard-expansion"></a>Développement des caractères génériques
## <a name="microsoft-specific"></a>Section spécifique à Microsoft  
 Vous pouvez utiliser des caractères génériques (le point d’interrogation (?) et l’astérisque (*)) pour spécifier des arguments de nom de fichier et de chemin d’accès sur la ligne de commande.  
  
 Arguments de ligne de commande sont gérés par une routine appelée **_setargv** (ou **_wsetargv** dans l’environnement à caractères larges), qui par défaut ne développe pas les caractères génériques en chaînes séparées dans le `argv`tableau de chaînes. Pour plus d’informations sur l’activation du développement des caractères génériques, consultez [développement les Arguments génériques](../c-language/expanding-wildcard-arguments.md).  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [main : démarrage du programme](../cpp/main-program-startup.md)