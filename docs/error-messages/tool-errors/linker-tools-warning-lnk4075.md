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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e8c3330e637ae0e0dce5e875fcc349c6deefcf27
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4075"></a>Avertissement des outils Éditeur de liens LNK4075
en ignorant les « option1 » en raison d’une spécification de « option2 »  
  
 La deuxième option substitue la première.  
  
 Options de l’éditeur de liens s’excluent mutuellement sont spécifiées.  Examinez vos options de l’éditeur de liens.  Où les options de l’éditeur de liens sont spécifiées dépend de la façon dont vous générez votre projet.  
  
-   Si vous créez dans l’environnement de développement, recherchez dans les pages de propriétés de l’éditeur de liens pour votre projet et voir où les deux options de l’éditeur de liens sont spécifiées.  Consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md) pour plus d’informations.  
  
-   Si vous générez sur la ligne de commande, consultez les options de l’éditeur de liens spécifiées.  
  
-   Si vous générez des scripts de build, parcourez vos scripts pour voir où ces options de l’éditeur de liens sont spécifiées.  
  
 Lorsque vous trouvez où les options de l’éditeur de liens s’excluent mutuellement sont spécifiées, supprimez l’une des options de l’éditeur de liens.  
  
 Obtenir des exemples spécifiques :  
  
-   Si vous liez un module qui a été compilé avec **/Zi**, ce qui implique une option de l’éditeur de liens interne appelée /EDITANDCONTINUE et un module qui a été compilé avec/OPT : REF, / OPT : ICF ou/INCREMENTAL : no, qui n’impliquent aucun /EDITANDCONTINUE, vous allez obtenir LNK4075.  Consultez [/Z7, / Zi, /ZI (Format des informations de débogage)](../../build/reference/z7-zi-zi-debug-information-format.md) pour plus d’informations.