---
title: Avertissement du compilateur C4335 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4335
dev_langs:
- C++
helpviewer_keywords:
- C4335
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
caps.latest.revision: 12
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: dc8436664038d3f53f3a01d5006c41c3d0e4c8f0
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="compiler-warning-c4335"></a>Avertissement du compilateur C4335
Format de fichier Mac détecté : convertissez le fichier source au format DOS ou UNIX  
  
 Le caractère de fin de ligne de la première ligne d’un fichier source est de style Macintosh ('\r') par opposition à UNIX ('\n') ou à DOS ('\r\n').  
  
 Cet avertissement est toujours émis en tant qu’erreur.  Consultez [avertissement](../../preprocessor/warning.md) pragma pour plus d’informations sur la manière de désactiver cet avertissement.  En outre, cet avertissement est émis uniquement une fois par compiland. Par conséquent, s’il existe plusieurs `#include` directives qui spécifient des fichiers au format Macintosh, C4335 est générée qu’une seule fois.  
  
 Une façon de générer des fichiers au format Macintosh consiste à l’aide de la **Options d’enregistrement avancées** (sur le **fichier** menu) dans Visual Studio.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C4335.  
  
```  
// C4335 expected  
#include "c4335.h"   // assume both include files are in Macintosh format  
#include "c4335_2.h"  
```
