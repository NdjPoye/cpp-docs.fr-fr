---
title: Unicode dans MFC | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- wide characters, Unicode
- Unicode [MFC], MFC
- wide characters, encoding
- strings [MFC], Unicode
- Unicode [MFC], enabling
ms.assetid: 1002004b-4113-4380-bf63-e1570934b793
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bc7ac9a55818022a4238565ed4309fe96f7ec058
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="unicode-in-mfc"></a>Unicode dans MFC
MFC prend en charge la norme Unicode de codage des caractères larges sur les plateformes Windows NT, Windows 2000 et Windows XP. Les applications Unicode ne peut pas s’exécuter sur les plateformes Windows 98.  
  
 Les versions Unicode des bibliothèques MFC sont décrites ci-dessous :  
  
### <a name="static-link-libraries"></a>Bibliothèques de liens statiques  
  
|Version finale|Débogage|Description|  
|-------------|-----------|-----------------|  
|UAFXCW.lib, .pdb|UAFXCWD.lib, .pdb|Bibliothèque de liens statiques MFC Unicode|  
  
### <a name="dynamic-link-libraries"></a>Bibliothèques de liens dynamiques  
  
|Version finale|Débogage|Description|  
|-------------|-----------|-----------------|  
|MFC100U.lib, .dbg, def, .dll, .map, .pdb, .prf|MFC100UD.lib, .def, .dll, .map, .pdb|Bibliothèque d’importation MFC Unicode (consultez les remarques ci-dessous pour une explication des extensions de fichier)|  
|MFCS100U.lib, .pdb|MFCS100UD.lib, .pdb|Contenant le code qui doit être lié statiquement dans une application ou une DLL de bibliothèque d’importation MFC Unicode|  
  
 **Types de fichiers**  
  
-   Importer des fichiers de bibliothèque ont l’extension (.lib).  
  
-   Les fichiers de bibliothèque de liens dynamiques ont l’extension (.dll).  
  
-   Fichiers de module de définition (.def) sont des fichiers texte qui contiennent des instructions pour la définition d’un .exe ou .dll.  
  
-   Fichiers de mappage (.map) sont des fichiers texte qui contiennent des informations utilisées par l’éditeur de liens lors de la liaison d’un programme.  
  
-   Fichiers de bibliothèque (.lib) sont utilisés conjointement avec les versions de la DLL de MFC. Ces fichiers contiennent le code qui doit être lié de manière statique ou de l’application DLL.  
  
-   Fichiers de programme (.pdb) de la base de données contiennent des informations d’état de débogage et de projet.  
  
-   Fichiers de débogage (.dbg) contiennent des informations (COFF FPO et CodeView) utilisées par le débogueur Visual C++.  
  
 Pour plus d’informations sur les conventions d’affectation de noms, consultez [Conventions d’affectation de noms de la bibliothèque](../mfc/library-naming-conventions.md).  
  
 Pour plus d’informations sur l’utilisation d’Unicode avec MFC, consultez [chaînes : Unicode et la prise en charge de la valeur de caractère multioctets (MBCS)](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Concepts](../mfc/mfc-concepts.md)   
 [Rubriques MFC générales](../mfc/general-mfc-topics.md)

