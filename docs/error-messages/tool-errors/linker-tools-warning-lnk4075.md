---
title: "Avertissement LNK4075 des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4075
dev_langs:
- C++
helpviewer_keywords:
- LNK4075
ms.assetid: f39ad3f9-c263-4cf0-9d70-259fc56ac96d
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9dee257bec0f09bd729bf10c4a1468ecb20dfa61
ms.openlocfilehash: 84dea754a1d2268c92e703dd04b0169ccc258ab3
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-warning-lnk4075"></a>Avertissement des outils Éditeur de liens LNK4075
en ignorant les « option1 » en raison de la spécification de « option2 »  
  
 La deuxième option substitue la première.  
  
 Options de l’éditeur de liens s’excluent mutuellement sont spécifiées.  Examinez les options de l’éditeur de liens.  Où les options de l’éditeur de liens sont spécifiées dépend de la façon dont vous générez votre projet.  
  
-   Si vous programmez dans l’environnement de développement, recherchez dans les pages de propriétés de l’éditeur de liens pour votre projet et voir où les deux options de l’éditeur de liens sont spécifiées.  Consultez la page [utilisation des propriétés de projet](../../ide/working-with-project-properties.md) pour plus d’informations.  
  
-   Si vous générez à la ligne de commande, consultez les options de l’éditeur de liens spécifiées.  
  
-   Si vous générez des scripts de génération, parcourez vos scripts pour voir où ces options de l’éditeur de liens sont spécifiées.  
  
 Lorsque vous trouvez où les options de l’éditeur de liens s’excluent mutuellement sont spécifiées, supprimez une des options de l’éditeur de liens.  
  
 Voici quelques exemples spécifiques :  
  
-   Si vous liez un module compilé avec **/Zi**, ce qui implique une option de l’éditeur de liens interne appelée /EDITANDCONTINUE et un module compilé avec/OPT : REF, / OPT : ICF ou/INCREMENTAL : no, ce qui n’implique aucun /EDITANDCONTINUE, vous obtiendrez LNK4075.  Consultez la page [/Z7, / Zi, /ZI (Format des informations de débogage)](../../build/reference/z7-zi-zi-debug-information-format.md) pour plus d’informations.
