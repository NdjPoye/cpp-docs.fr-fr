---
title: "Créer un projet Linux C++ dans Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/15/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-linux
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d7c1d67-bc31-4f96-8622-2b4cf91372fd
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 8b9eda4c238ae1a3ea3e59d0e5c39ee6b59cff02
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="create-a-new-linux-project"></a>Créer un projet Linux
Quand vous développez pour Linux, vous avez la possibilité de créer un projet Visual Studio ou un projet CMake. Cette rubrique décrit comment créer un projet Visual Studio. Pour plus d’informations sur les projets CMake, consultez [Configurer un projet CMake Linux](cmake-linux-project.md).

Pour créer un projet Linux dans Visual Studio, effectuez les étapes suivantes :

1. Sélectionnez **Fichier > Nouveau projet** dans Visual Studio, ou appuyez sur **Ctrl+Maj+N**.
1. Sélectionnez le nœud **Visual C++ > Multiplateforme > Linux** et le type de projet que vous voulez créer, entrez un nom/emplacement, puis cliquez sur OK.

   ![Nouveau projet Linux](media/newproject.png)

   | Type de projet | Description
   | ------------ | ---
   | **Clignotement (Raspberry)**           | Projet ciblé pour un appareil Raspberry Pi avec un exemple de code écrit pour faire clignoter une LED
   | **Application console (Linux)** | Projet ciblé pour n’importe quel ordinateur Linux avec un exemple de code écrit afin de sortir un texte vers la console
   | **Projet vide (Linux)**       | Projet ciblé pour n’importe quel ordinateur Linux sans exemple de code écrit
   | **Projet Makefile (Linux)**    | Projet ciblé pour n’importe quel ordinateur Linux qui sera généré à l’aide d’un système de génération Makefile standard

