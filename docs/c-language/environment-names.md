---
title: "Noms d’environnement | Microsoft Docs"
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
ms.assetid: 9af409a5-e724-465a-9a21-88d3586c2e92
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 25c493f7f25b8fd1239aea70bcf059c4137b7bc3
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="environment-names"></a>Noms d'environnement
**ANSI 4.10.4.4** Jeu de noms d'environnement et méthode pour modifier la liste d'environnement utilisée par la fonction [getenv](../c-runtime-library/reference/getenv-wgetenv.md)  
  
 Le jeu de noms d'environnement est illimité.  
  
 Pour modifier les variables d'environnement à partir d'un programme C, appelez la fonction [_putenv](../c-runtime-library/reference/putenv-wputenv.md). Pour modifier des variables d'environnement à partir de la ligne de commande dans Windows, utilisez la commande SET (par exemple, SET LIB = D:\ LIBS).  
  
 Les variables d'environnement définies à partir du programme C existent uniquement si leur copie hôte du shell de commande du système d'exploitation est en cours d'exécution (CMD.EXE ou COMMAND.COM). Par exemple, la ligne  
  
```  
system( SET LIB = D:\LIBS );  
```  
  
 exécuterait une copie du shell de commande (CMD.EXE), définirait la variable d'environnement LIB, et reviendrait au programme C, en quittant la copie secondaire de CMD.EXE. Le fait de quitter cette copie de CMD.EXE supprime la variable d'environnement temporaire LIB.  
  
 De même, les modifications apportées par la fonction `_putenv` durent uniquement jusqu'à la fin du programme.  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions des bibliothèques](../c-language/library-functions.md)   
 [_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md)   
 [getenv, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)