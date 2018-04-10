---
title: Référence EDITBIN | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- editbin
dev_langs:
- C++
helpviewer_keywords:
- binary data, editing
- object files, modifying
- EDITBIN program
- COFF files, editing
ms.assetid: efdda03b-3dfc-4d31-90e6-caf5b3977914
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e0ff9c0c58498361764dcc1b6c454c9b629d9bed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="editbin-reference"></a>Référence EDITBIN
L’éditeur de fichiers binaires Microsoft COFF (EDITBIN. (EXE) modifie les fichiers binaires de fichier Format COFF (Common Object). Vous pouvez y recourir pour modifier des fichiers objets, les fichiers exécutables et les bibliothèques de liens dynamiques (DLL).  
  
> [!NOTE]
>  Vous pouvez démarrer cet outil uniquement à partir de l'invite de commandes [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]. Vous ne pouvez pas le démarrer à partir d'une invite de commandes système ni de l'Explorateur de fichiers.  
  
 EDITBIN n’est pas disponible pour les fichiers générés par le [/GL](../../build/reference/gl-whole-program-optimization.md) option du compilateur. Les modifications apportées à des fichiers binaires produits avec /GL devra être obtenue en recompilation et la liaison.  
  
-   [Ligne de commande EDITBIN](../../build/reference/editbin-command-line.md)  
  
-   [Options EDITBIN](../../build/reference/editbin-options.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Outils de génération C/C++](../../build/reference/c-cpp-build-tools.md)