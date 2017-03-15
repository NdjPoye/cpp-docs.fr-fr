---
title: "Erreur des outils &#201;diteur de liens LNK1211 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1211"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1211"
ms.assetid: 607400eb-4180-4892-817f-eedfa628af61
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur des outils &#201;diteur de liens LNK1211
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

informations de type précompilé non trouvées ; 'NomFichier' n'a pas été lié ou a été remplacé  
  
 Le fichier objet donné, compilé avec [\/Yc](../../build/reference/yc-create-precompiled-header-file.md), n'a pas été spécifié dans la commande LINK ou a été remplacé.  
  
 Si vous créez une bibliothèque de débogage qui utilise des en\-têtes précompilés et si vous spécifiez \/Yc et [\/Z7](../../build/reference/z7-zi-zi-debug-information-format.md), Visual C\+\+ génère un fichier objet précompilé qui contient des informations de débogage pour CodeView.  L'erreur ne survient que quand vous placez l'objet précompilé dans une bibliothèque, utilisez la bibliothèque pour construire une image exécutable, et que les fichiers objet référencés n'ont pas de référence transitive à aucune des fonctions que le fichier objet précompilé définit.  
  
 Il y a deux méthodes pour éviter cette situation :  
  
-   Spécifiez l'option du compilateur [\/Yd](../../build/reference/yd-place-debug-information-in-object-file.md) pour ajouter les informations CodeView de l'en\-tête précompilé à chaque module objet.  Cette méthode est moins intéressante parce qu'elle produit généralement des modules objets de grande taille qui peuvent augmenter le temps nécessaire pour l'édition de liens de l'application.  
  
-   Spécifiez [\/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) et passez le nom d'une chaîne arbitraire lors de la création d'un fichier d'en\-tête précompilé ne contenant aucune définition de fonction.  Ceci conduit le compilateur à créer un symbole dans le fichier d'objet précompilé et à émettre une référence à ce symbole dans chaque fichier objet qui utilise le fichier d'en\-tête précompilé associé au fichier objet précompilé.  
  
 Quand vous compilez un module avec **\/Yc** et **\/Yl**, le compilateur crée un symbole se présentant comme `__@@_PchSym_@00@...@symbol_name`, où les points de suspension \(...\) représentent une chaîne de caractères générée par le compilateur, et le stocke dans le module objet.  Tout fichier source que vous compilez avec cet en\-tête précompilé fait référence au symbole spécifié, ce qui amène l'éditeur de liens à incorporer le module objet et ses informations de débogage à partir de la bibliothèque.  
  
 Pour plus d'informations sur cette erreur, consultez dans la Base de Connaissances l'article Q102697 PRB : Build Errors Using Precompiled Header in Debugging Lib \(article en anglais\).