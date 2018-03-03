---
title: "Prise en charge Unicode dans le compilateur et l’éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 12/15/2017
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.UseUnicodeResponseFiles
- VC.Project.VCLibrarianTool.UseUnicodeResponseFiles
- VC.Project.VCCLCompilerTool.UseUnicodeResponseFiles
- VC.Project.VCXDCMakeTool.UseUnicodeResponseFiles
dev_langs:
- C++
helpviewer_keywords:
- Unicode, Visual C++
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fe775a53914089648a868a94aa2c863ee87790c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="unicode-support-in-the-compiler-and-linker"></a>Prise en charge Unicode dans le compilateur et l'éditeur de liens

La plupart des outils de génération Visual C++ prend en charge Unicode entrées et sorties.

## <a name="filenames"></a>Noms de fichiers

Les noms de fichier spécifiés sur la ligne de commande ou dans les directives du compilateur (tel que `#include`) peut contenir des caractères Unicode.

## <a name="source-code-files"></a>Fichiers de code source

Les caractères Unicode sont prises en charge dans les identificateurs, les macros, les littéraux de chaîne et de caractère et dans les commentaires.  Noms de caractères universels sont également pris en charge.

Unicode peuvent être entré dans un fichier de code source dans les encodages suivants :

- UTF-16 little endian avec ou sans marque d’ordre d’octet (BOM)

- UTF-16 big endian avec ou sans BOM

- UTF-8 avec BOM

## <a name="output"></a>Sortie

Lors de la compilation, le compilateur génère des diagnostics dans la console au format UTF-16.  Les caractères qui peuvent être affichés à votre console dépendent des propriétés de la fenêtre de console.  Sortie du compilateur redirigée vers un fichier est dans la page de codes de console ANSI actuelle.

## <a name="linker-response-files-and-def-files"></a>Fichiers de réponse de l’éditeur de liens et. Fichiers DEF

Fichiers réponse et les fichiers DEF peuvent être soit UTF-16 avec une marque BOM ou ANSI.

## <a name="asm-and-cod-dumps"></a>dumps .asm et .cod

les dumps .asm et .cod sont au format ANSI par défaut pour la compatibilité avec MASM. Utilisez [/FAu](../../build/reference/fa-fa-listing-file.md) de sortie UTF-8. Notez que si vous spécifiez **/FAS**, la source par recoupement sera directement affichée et peut sembler altérée, par exemple, si vous n’avez pas spécifié et que le code source est UTF-8 **/FAsu**.

## <a name="see-also"></a>Voir aussi

[Générer du code C/C++ sur la ligne de commande](../../build/building-on-the-command-line.md)