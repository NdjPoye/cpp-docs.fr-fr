---
title: "Options de lien | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "nothrownew.obj"
  - "newmode.obj"
  - "noenv.obj"
  - "psetargv.obj"
  - "loosefpmath.obj"
  - "smallheap.obj"
  - "fp10.obj"
  - "nochkclr.obj"
  - "chkstk.obj"
  - "pcommode.obj"
  - "pnoenv.obj"
  - "options de lien (C++)"
  - "invalidcontinue.obj"
  - "pnothrownew.obj"
  - "pwsetargv.obj"
  - "pinvalidcontinue.obj"
  - "wsetargv.obj"
  - "binmode.obj"
  - "setargv.obj"
  - "noarg.obj"
  - "pnewmode.obj"
  - "commode.obj"
  - "pthreadlocale.obj"
  - "pbinmode.obj"
  - "threadlocale.obj"
  - "pnoarg.obj"
ms.assetid: 05b5a77b-9dd1-494b-ae46-314598c770bb
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Options de lien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le répertoire CRT lib inclut plusieurs petits fichiers objet qui permettent aux fonctionnalités spécifiques à CRT sans modification du code.  Elles sont appelées « options de lien » car que vous devez les ajouter à la ligne de commande de l'éditeur de liens à utiliser.  
  
 Les versions simples en mode ont été ajoutées.  Utilisez les versions standard pour le mode natif et le code de \/clr, utilisez les versions simples \(le préfixe un p\) pour le mode d'\/clr:pure.  
  
|Natif et \/clr|Mode pur|Description|  
|--------------------|--------------|-----------------|  
|binmode.obj|pbinmode.obj|Définit le mode par défaut de FILE\- traduction en binaire.  Consultez [\_fmode](../c-runtime-library/fmode.md).|  
|chkstk.obj|N\/A|Prend en charge la vérification de pile et d'allocation si AWE hors d'utilisation de CRT.|  
|commode.obj|pcommode.obj|Définit l'indicateur global de validation « pour valider ».  Consultez [fopen, \_wfopen](../c-runtime-library/reference/fopen-wfopen.md) et [fopen\_s, \_wfopen\_s](../c-runtime-library/reference/fopen-s-wfopen-s.md).|  
|fp10.obj|N\/A|Modifie le contrôle par défaut de précision de 64 bits.  Consultez [Prise en charge de la virgule flottante](../c-runtime-library/floating-point-support.md).|  
|invalidcontinue.obj|pinvalidcontinue.obj|Définit un gestionnaire par défaut des paramètres non valides qui ne fait rien, ce qui signifie que les paramètres non valides transmis aux fonctions CRT définiront seulement errno et retourne un résultat d'erreur.|  
|loosefpmath.obj|N\/A|Vérifie que le code à virgule flottante tolère des valeurs denormal.|  
|newmode.obj|pnewmode.obj|Fait d'appeler [malloc](../c-runtime-library/reference/malloc.md) le gestionnaire en cas de échec.  Consultez [\_set\_new\_mode](../c-runtime-library/reference/set-new-mode.md), [\_set\_new\_handler](../c-runtime-library/reference/set-new-handler.md), [calloc](../c-runtime-library/reference/calloc.md) et [realloc](../c-runtime-library/reference/realloc.md).|  
|noarg.obj|pnoarg.obj|Désactive tout le traitement de l'argc et l'argv.|  
|nochkclr.obj|N\/A|Ne fait rien.  Supprimez de vos projets.|  
|noenv.obj|pnoenv.obj|Désactive la création d'un environnement mis en cache pour CRT.|  
|nothrownew.obj|pnothrownew.obj|Vérifie la version non levée de nouveau dans le CRT.  Consultez [Opérateurs new et delete](../cpp/new-and-delete-operators.md).|  
|setargv.obj|psetargv.obj|Active l'expansion de caractère générique d'argument de ligne de commande.  Consultez [Développement des arguments avec caractères génériques](../c-language/expanding-wildcard-arguments.md).|  
|smallheap.obj|N\/A|Installe un petit gestionnaire de segment très simple.|  
|threadlocale.obj|pthreadlocale.obj|Active les paramètres régionaux par thread pour tous les nouveaux threads par défaut.|  
|wsetargv.obj|pwsetargv.obj|Active l'expansion de caractère générique d'argument de ligne de commande.  Consultez [Développement des arguments avec caractères génériques](../c-language/expanding-wildcard-arguments.md).|  
  
## Voir aussi  
 [Fonctions de bibliothèque CRT](../c-runtime-library/crt-library-features.md)