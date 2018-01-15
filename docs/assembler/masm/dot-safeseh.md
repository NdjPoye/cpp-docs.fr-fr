---
title: . SAFESEH | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .SAFESEH
dev_langs: C++
helpviewer_keywords:
- registering functions as exception handlers
- SAFESEH directive
- .SAFESEH directive
ms.assetid: 6eaac8c4-c46f-47ae-8a66-f5cfeb267e43
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 09a1848ce12eba4cf0ba08d0898e135d70e14fe1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="safeseh"></a>.SAFESEH
Enregistre une fonction en tant que gestionnaire d’exceptions structuré.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
.SAFESEH identifier  
```  
  
## <a name="remarks"></a>Notes  
 *identificateur* doit être l’ID pour un défini localement [PROC](../../assembler/masm/proc.md) ou [EXTRN](../../assembler/masm/extrn.md) PROC. A [étiquette](../../assembler/masm/label-masm.md) n’est pas autorisée. La barre d’outils. SAFESEH (directive) nécessite le [/safeseh](../../assembler/masm/ml-and-ml64-command-line-reference.md) l’option de ligne de commande ml.exe.  
  
 Pour plus d’informations sur les gestionnaires de la gestion structurée des exceptions, consultez [/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md).  
  
 Par exemple, pour inscrire un gestionnaire d’exceptions sécurisés, créez un nouveau fichier MASM (comme suit), assembler avec l’option /safeseh et l’ajouter à des objets liés.  
  
```  
.386  
.model  flat  
MyHandler   proto  
.safeseh    MyHandler  
end  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les directives](../../assembler/masm/directives-reference.md)