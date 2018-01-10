---
title: ALIAS (MASM) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Alias
dev_langs: C++
helpviewer_keywords: ALIAS directive
ms.assetid: d9725c49-58de-41da-ab01-b06a56cf5cf2
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 59dc4fd5481b22e69153c68e94a81b2887118ebc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="alias-masm"></a>ALIAS (MASM)
Le **ALIAS** directive crée un autre nom pour une fonction.  Cela vous permet de créer plusieurs noms pour une fonction, ou créer des bibliothèques qui permettent de l’éditeur de liens (LINK.exe) pour mapper une fonction ancienne vers une nouvelle fonction.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
ALIAS  <  
alias  
> = <  
actual-name  
>  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 `actual-name`  
 Le nom réel de la fonction ou la procédure.  Les crochets sont requis.  
  
 `alias`  
 Le nom de remplacement ou l’alias.  Les crochets sont requis.  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les directives](../../assembler/masm/directives-reference.md)