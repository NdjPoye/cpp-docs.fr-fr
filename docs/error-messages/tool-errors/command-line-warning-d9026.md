---
title: Avertissement de ligne de commande D9026 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: D9026
dev_langs: C++
helpviewer_keywords: D9026
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9127ad1887d476e5460798f806c2db1ff3144de3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="command-line-warning-d9026"></a>Avertissement de ligne de commande D9026
options s’appliquent à toute ligne de commande  
  
 Une option a été spécifiée sur une commande après qu’un nom de fichier a été spécifié. L’option a été appliquée au fichier qui l’ont précédé.  
  
 Par exemple, dans la commande  
  
```  
CL verdi.c /G5 puccini.c  
```  
  
 le fichier VERDI.c qui est compilé à l’aide de l’option/G5, pas la valeur par défaut/G4.  
  
 Ce comportement est différent de celui des versions précédentes, ce qui est appliqué uniquement les options spécifiées avant le nom de fichier, qui résulte de VERDI.c par qui est compilé à l’aide de/G4 et Puccini.c par qui est compilé à l’aide / G5.