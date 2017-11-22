---
title: "Compatibilité binaire C++ entre Visual Studio 2015 et Visual Studio 2017 | Microsoft Docs"
ms.custom: 
ms.date: 09/21/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 89bb772976050c8ebf0b7745aa0541c2de3e2fed
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="c-binary-compatibility-between-visual-studio-2015-and-visual-studio-2017"></a>Compatibilité binaire C++ entre Visual Studio 2015 et Visual Studio 2017


Dans les versions précédentes de Visual Studio, la compatibilité binaire entre les fichiers objets (OBJ), les bibliothèques statiques (LIB), les bibliothèques dynamiques (DLL) et les fichiers exécutables (EXE) générés avec différentes versions de l’ensemble d’outils du compilateur et des bibliothèques runtime n’était pas garantie. Ce n’est plus le cas dans Visual Studio 2017. Dans Visual Studio 2015 et Visual Studio 2017, le numéro majeur de l’ensemble d’outils C++ est 14 (v140 pour Visual Studio 2015 et v141 pour Visual Studio 2017). Ce qui veut dire que les bibliothèques runtime et les applications compilées avec l’une des versions du compilateur sont, pour la plupart, binairement compatibles. Par exemple, vous pouvez créer une DLL dans Visual Studio 2017 et l’utiliser à partir d’une application compilée avec Visual Studio 2015 ou utiliser les bibliothèques redistribuables Visual Studio 2017 avec votre application générée à l’aide de l’ensemble d’outils 2015.  

Il existe deux exceptions à cette règle. La compatibilité binaire n’est pas garantie dans les cas suivants :  

1) Quand les bibliothèques statiques ou les fichiers objets sont compilés avec le commutateur de compilateur /GL.  

2) Quand une application consomme des bibliothèques redistribuables dont le numéro de version est inférieur à l’ensemble d’outils utilisé pour compiler l’application. En d’autres termes, si vous compilez un programme avec l’ensemble d’outils de plateforme v141, toutes les bibliothèques redistribuables que consomme l’application doivent être compilées avec v141 ou supérieur.  

## <a name="see-also"></a>Voir aussi  

[Historique des modifications de Visual C++](..\porting\visual-cpp-change-history-2003-2015.md)


