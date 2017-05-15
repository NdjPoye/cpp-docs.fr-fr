---
title: "Erreur irrécupérable C1052 | Documents Microsoft"
ms.custom: 
ms.date: 05/08/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1052
dev_langs:
- C++
helpviewer_keywords:
- C1052
ms.assetid: f2c09a2f-d3c1-4420-9501-ffcb65caf87b
caps.latest.revision: 0
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
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: f3ab91c1c79b822a4d9a33fb0ab5fbd88146fff0
ms.contentlocale: fr-fr
ms.lasthandoff: 05/10/2017

---
# <a name="fatal-error-c1052"></a>Erreur irrécupérable C1052
fichier de base de données de programme, «*nom de fichier*', a été généré par l’éditeur de liens avec/Debug : Fastlink ; compilateur ne peut pas mettre à jour ces fichiers PDB ; supprimez-le ou utilisez /Fd pour spécifier un autre nom de fichier PDB  
  
Le compilateur ne peut pas mettre à jour les fichiers du même programme (PDB) de la base de données qui sont générés par l’éditeur de liens lors de la [/Debug : Fastlink](../../build/reference/debug-generate-debug-info.md) option est spécifiée. Normalement les fichiers PDB généré par le compilateur et les fichiers PDB généré par l’éditeur de liens ont des noms différents. Toutefois, s’ils sont définis pour utiliser les mêmes noms, cette erreur peut résulter.  
  
Pour résoudre ce problème, vous pouvez supprimer les fichiers PDB explicitement avant que vous compilez à nouveau, ou vous pouvez créer des noms différents pour les fichiers PDB généré par le compilateur et générées par l’éditeur de liens. Pour créer différents noms de fichier PDB généré par le compilateur sur la ligne de commande, utilisez le [/Fd](../../build/reference/fd-program-database-file-name.md) option. Pour générer des noms de fichier PDB différents dans l’IDE, ouvrez le **Pages de propriétés** boîte de dialogue pour votre projet et dans le **propriétés de Configuration**, **C/C++**, **fichiers de sortie** , définissez le **nom de fichier de base de données de programme** propriété. Par défaut, cette propriété est `$(IntDir)vc$(PlatformToolsetVersion).pdb`. Vous pouvez également définir le nom de fichier PDB généré par l’éditeur de liens. Ouvrez le **Pages de propriétés** boîte de dialogue pour votre projet et dans le **propriétés de Configuration**, **l’éditeur de liens**, **débogage** , définissez le **générer un fichier de base de données de programme** propriété. Par défaut, cette propriété est définie `$(OutDir)$(TargetName).pdb`.  

