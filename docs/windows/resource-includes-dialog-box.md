---
title: "Boîte de dialogue Include des ressources | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.resourceincludes
dev_langs: C++
helpviewer_keywords:
- Resource Includes dialog box
- rc files, changing storage
- symbol header files, changing
- compiling source code, including resources
- .rc files, changing storage
- symbol header files, read-only
- symbols, symbol header files
ms.assetid: 659a54e6-e416-4045-8411-798730ff4ce3
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 610e970ad84c6c89d91182b7a61bb759112fcd7d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-includes-dialog-box"></a>Include des ressources (boîte de dialogue)
Vous pouvez utiliser la **Include des ressources** boîte de dialogue pour modifier la disposition de l’environnement de travail classique de stockage de toutes les ressources dans le fichier .rc du projet et tous les [symboles](../windows/symbols-resource-identifiers.md) dans Resource.h.  
  
 Pour ouvrir la **Include des ressources** de fichiers dans la boîte de dialogue, avec le bouton droit une .rc [affichage des ressources](../windows/resource-view-window.md), puis choisissez **Include des ressources** dans le menu contextuel.  
  
 **Fichier d’en-tête de symbole**  
 Vous permet de modifier le nom du fichier d'en-tête où sont stockées les définitions de symbole de votre fichier de ressources. Pour plus d’informations, consultez [la modification des noms de symbole de fichiers d’en-tête](../windows/changing-the-names-of-symbol-header-files.md).  
  
 **Directives de symboles en lecture seule**  
 Vous permet d'inclure les fichiers d'en-tête qui contiennent les symboles à ne pas modifier durant une session d'édition. Par exemple, vous pouvez inclure un fichier de symboles partagé entre plusieurs projets. Vous pouvez également inclure des fichiers MFC .h. Pour plus d’informations, consultez [symboles notamment partagés (lecture seule) ou calculés](../windows/including-shared-read-only-or-calculated-symbols.md).  
  
 **Directives de compilation**  
 Vous permet d’inclure des fichiers de ressources qui sont créés et modifiés à l’écart des ressources de votre fichier de ressources principal, qui contiennent des directives au moment de la compilation (comme celles qui incluent des ressources de manière conditionnelle) ou qui contiennent des ressources dans un format personnalisé. Vous pouvez également utiliser la zone Directives au moment de la compilation pour inclure des fichiers de ressources MFC standard. Pour plus d’informations, consultez [, y compris des ressources au moment de la compilation](../windows/how-to-include-resources-at-compile-time.md).  
  
> [!NOTE]
>  Entrées de ces zones de texte apparaissent dans le fichier .rc marqué par `TEXTINCLUDE 1`, `TEXTINCLUDE 2`, et `TEXTINCLUDE 3` respectivement. Pour plus d’informations, consultez [TN035 : à l’aide de plusieurs fichiers de ressources et les fichiers d’en-tête avec Visual C++](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md).  
  
 Une fois que vous avez apporté des modifications à votre fichier de ressources à l’aide de la **Include des ressources** boîte de dialogue, vous devez fermer le fichier .rc et rouvrez-le pour que les modifications prennent effet. Pour plus d’informations, consultez [, y compris des ressources au moment de la compilation](../windows/how-to-include-resources-at-compile-time.md).  
  

  
## <a name="requirements"></a>Configuration requise  
 Win32  
  
## <a name="see-also"></a>Voir aussi  
 [Comment : spécifier les répertoires Include pour les ressources](../windows/how-to-specify-include-directories-for-resources.md)   
 [Symboles : Identificateurs de ressources](../windows/symbols-resource-identifiers.md)   
 [Fichiers de ressources](../windows/resource-files-visual-studio.md)   
 [Éditeurs de ressources](../windows/resource-editors.md)