---
title: -INTEGRITYCHECK | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /INTEGRITYCHECK
dev_langs: C++
helpviewer_keywords:
- -INTEGRITYCHECK editbin options
- /INTEGRITYCHECK editbin options
- INTEGRITYCHECK editbin options
ms.assetid: 2a293705-4396-421b-a5a5-693b4b867a85
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 20fa72f8cc2d12c719f0e50c250052a191b5ee81
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="integritycheck"></a>/INTEGRITYCHECK
Spécifie que la signature numérique de l’image binaire doit être vérifiée au moment du chargement.  
  
```  
  
/INTEGRITYCHECK[:NO]  
```  
  
## <a name="remarks"></a>Remarques  
 Dans l’en-tête du fichier DLL ou du fichier exécutable, cette option définit un indicateur qui requiert une vérification de signature numérique par le Gestionnaire de mémoire pour charger l’image de Windows. Les versions de Windows antérieures à Windows Vista ignorent cet indicateur. Cette option doit être définie pour les dll 64 bits qui implémentent de code en mode noyau et sont recommandées pour tous les pilotes de périphérique. Pour plus d’informations, consultez [procédure pas à pas en Mode noyau Code signature](http://go.microsoft.com/fwlink/?linkid=237093) sur le site Web MSDN.  
  
## <a name="see-also"></a>Voir aussi  
 [Options EDITBIN](../../build/reference/editbin-options.md)