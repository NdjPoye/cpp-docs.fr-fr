---
title: Erreur du compilateur C2220 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2220
dev_langs: C++
helpviewer_keywords: C2220
ms.assetid: d610802c-64d7-40ad-a2a6-0ed0b6815a6c
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dc31519b2153c66ea9bab42f536ba7c6be5b2a10
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2220"></a>Erreur du compilateur C2220
Avertissement considéré comme une erreur - aucun fichier objet généré  
  
 [/WX](../../build/reference/compiler-option-warning-level.md) indique au compilateur de traiter tous les avertissements comme des erreurs. Car une erreur s’est produite, aucun objet ou le fichier exécutable a été généré.  
  
 Cette erreur apparaît uniquement lorsque le **/WX** indicateur est défini et un avertissement se produit pendant la compilation. Pour corriger cette erreur, vous devez éliminer chaque avertissement dans votre projet.  
  
### <a name="to-fix-use-one-of-the-following-techniques"></a>Pour résoudre le problème, utilisez une des techniques suivantes  
  
-   Résoudre les problèmes qui provoquent des avertissements dans votre projet.  
  
-   Compiler à un niveau d’avertissement inférieur, par exemple, utilisez **/W3** au lieu de **/W4**.  
  
-   Utilisez un [avertissement](../../preprocessor/warning.md) pragma pour désactiver ou supprimer un avertissement spécifique.  
  
-   N’utilisez pas **/WX** à compiler.