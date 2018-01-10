---
title: "Vue d’ensemble de LIB | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Lib
dev_langs: C++
helpviewer_keywords: LIB [C++], modes
ms.assetid: e997d423-f574-434f-8b56-25585d137ee0
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ef3d1e57371fdea62bb557830baca633f4165637
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="overview-of-lib"></a>Vue d'ensemble de LIB
LIB crée des bibliothèques standard, des bibliothèques d’importation et exportation de fichiers, vous pouvez utiliser avec [lien](../../build/reference/linker-options.md) lors de la création d’un programme. LIB s’exécute à partir d’une invite de commandes.  
  
 Vous pouvez utiliser LIB dans les modes suivants :  
  
-   [Création ou modification d’une bibliothèque COFF](../../build/reference/managing-a-library.md)  
  
-   [Extraction d’un objet membre vers un fichier](../../build/reference/extracting-a-library-member.md)  
  
-   [Création d’un fichier d’exportation et d’une bibliothèque d’importation](../../build/reference/working-with-import-libraries-and-export-files.md)  
  
 Ces modes s’excluent mutuellement ; Vous pouvez utiliser LIB dans un seul mode à la fois.  
  
## <a name="lib-options"></a>Options de lib  
 Le tableau suivant répertorie les options de lib.exe, avec un lien vers plus d’informations.  
  
 **/ DEF**  
 Créer une bibliothèque d’importation et d’un fichier d’exportation.  
  
 Pour plus d’informations, consultez [création d’une bibliothèque d’importation et d’un fichier d’exportation](../../build/reference/building-an-import-library-and-export-file.md).  
  
 **/ ERRORREPORT**  
 Envoyer des informations à Microsoft sur les erreurs internes avec lib.exe.  
  
 Pour plus d’informations, consultez [en cours d’exécution de LIB](../../build/reference/running-lib.md).  
  
 **/ EXPORT**  
 Exporte une fonction à partir de votre programme.  
  
 Pour plus d’informations, consultez [création d’une bibliothèque d’importation et d’un fichier d’exportation](../../build/reference/building-an-import-library-and-export-file.md).  
  
 **ET L’EXTRACTION**  
 Créez un fichier objet (.obj) qui contient une copie d’un membre d’une bibliothèque existante.  
  
 Pour plus d’informations, consultez [extraction d’un membre de la bibliothèque](../../build/reference/extracting-a-library-member.md).  
  
 **/ INCLURE**  
 Ajoute un symbole à la table de symboles.  
  
 Pour plus d’informations, consultez [création d’une bibliothèque d’importation et d’un fichier d’exportation](../../build/reference/building-an-import-library-and-export-file.md).  
  
 **/ LIBPATH**  
 Substitue le chemin d’accès de la bibliothèque d’environnement.  
  
 Pour plus d’informations, consultez [gestion d’une bibliothèque](../../build/reference/managing-a-library.md).  
  
 **/ LISTE**  
 Affiche des informations sur la bibliothèque de sortie vers une sortie standard.  
  
 Pour plus d’informations, consultez [gestion d’une bibliothèque](../../build/reference/managing-a-library.md).  
  
 **/ LTCG**  
 Provoque la bibliothèque à l’aide de la génération de code de l’édition de liens.  
  
 Pour plus d’informations, consultez [en cours d’exécution de LIB](../../build/reference/running-lib.md).  
  
 **/ MACHINE**  
 Spécifie la plateforme cible pour le programme.  
  
 Pour plus d’informations, consultez [en cours d’exécution de LIB](../../build/reference/running-lib.md).  
  
 **/ NOM**  
 Lorsque vous créez une bibliothèque d’importation, spécifie le nom de la DLL pour laquelle la bibliothèque d’importation est générée.  
  
 Pour plus d’informations, consultez [gestion d’une bibliothèque](../../build/reference/managing-a-library.md).  
  
 **/ NODEFAULTLIB**  
 Supprime une ou plusieurs bibliothèques par défaut de la liste des bibliothèques qu’elle parcourt lors de la résolution des références externes.  
  
 Pour plus d’informations, consultez [gestion d’une bibliothèque](../../build/reference/managing-a-library.md).  
  
 **/NOLOGO**  
 Supprime l’affichage de la LIB copyright message et numéro de version et empêche l’affichage des fichiers de commandes.  
  
 Pour plus d’informations, consultez [en cours d’exécution de LIB](../../build/reference/running-lib.md).  
  
 **/ ENTRÉE SORTIE**  
 Remplace le nom de fichier de sortie par défaut.  
  
 Pour plus d’informations, consultez [gestion d’une bibliothèque](../../build/reference/managing-a-library.md).  
  
 **/ SUPPRESSION**  
 Omet un objet de la bibliothèque de sortie.  
  
 Pour plus d’informations, consultez [gestion d’une bibliothèque](../../build/reference/managing-a-library.md).  
  
 **/ SOUS-SYSTÈME**  
 Indique le système d’exploitation comment exécuter un programme créé par la liaison à la bibliothèque de sortie.  
  
 Pour plus d’informations, consultez [gestion d’une bibliothèque](../../build/reference/managing-a-library.md).  
  
 **/VERBOSE**  
 Affiche des détails sur la progression de la session, y compris les noms des fichiers .obj ajoutés.  
  
 Pour plus d’informations, consultez [en cours d’exécution de LIB](../../build/reference/running-lib.md).  
  
 **/WX**  
 Considérer les avertissements comme des erreurs.  
  
 Pour plus d’informations, consultez [en cours d’exécution de LIB](../../build/reference/running-lib.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Référence LIB](../../build/reference/lib-reference.md)   
 [Fichiers d’entrée LIB](../../build/reference/lib-input-files.md)   
 [Fichiers de sortie LIB](../../build/reference/lib-output-files.md)   
 [Autre sortie LIB](../../build/reference/other-lib-output.md)   
 [Structure d’une bibliothèque](../../build/reference/structure-of-a-library.md)