---
title: "LNK1302 d’erreur des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1302
dev_langs:
- C++
helpviewer_keywords:
- LNK1302
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2a5b9201608d6d457288c7ade9376147da08bcb9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1302"></a>Erreur des outils Éditeur de liens LNK1302
uniquement prise en charge de liaison de .netmodules sécurisés ; Impossible de lier le fichier .netmodule  
  
 Un fichier .netmodule (compilé avec **/LN**) a été passé à l’éditeur de liens dans un utilisateur tente d’appeler la liaison MSIL.  Un module C++ est valide pour la liaison MSIL s’il est compilé avec **/CLR : safe**.  
  
 Pour corriger cette erreur, compilez avec **/CLR : safe** afin d’activer la liaison MSIL ou passez le **/CLR** ou **/CLR : pure** fichier .obj afin de l’éditeur de liens au lieu du module.  
  
 Pour plus d'informations, consultez  
  
-   [/LN (créer un Module MSIL)](../../build/reference/ln-create-msil-module.md)  
  
-   [Fichiers .netmodule en tant qu’entrée de l’Éditeur de liens](../../build/reference/netmodule-files-as-linker-input.md)