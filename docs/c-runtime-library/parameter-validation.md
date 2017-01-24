---
title: "Validation de param&#232;tre | Microsoft Docs"
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
  - "paramètres, validation"
ms.assetid: 019dd5f0-dc61-4d2e-b4e9-b66409ddf1f2
caps.latest.revision: 9
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Validation de param&#232;tre
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les fonctions sécurisées CRT et de nombreuses fonctions préexistantes valident les paramètres.  Cela peut inclure le fait d'activer les pointeurs de valeur NULL, vérifier que les entiers sont dans une plage valide, ou vérifier que les valeurs d'énumération est valide.  Lorsqu'un paramètre non valide est trouvé, le gestionnaire de paramètre non valide est exécuté.  
  
## Routine du gestionnaire de paramètre non valide  
 Le comportement du runtime C lorsqu'un paramètre non valide est trouvé consiste à appeler le gestionnaire actuellement affecté de paramètre non valide.  Le paramètre non valide par défaut appelle les rapports d'incident Watson, ce qui entraîne l'application de suppression non ordonnées et demander à l'utilisateur qu'ils souhaitent charger le vidage sur incident à Microsoft pour l'analyse.  En mode débogage, un paramètre non valide a également provoque une assertion.  
  
 Ce comportement peut être modifié à l'aide de la fonction [\_set\_invalid\_parameter\_handler, \_set\_thread\_local\_invalid\_parameter\_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) pour définir le gestionnaire de paramètre non valide à votre propre fonction.  Si la fonction que vous spécifiez ne met pas l'application, le contrôle est renvoyé à la fonction qui a reçu les paramètres non valides, et ces fonctions normalement s'arrêtent l'exécution, retournent un code d'erreur, et `errno` défini à un code d'erreur.  Dans de nombreux cas, la valeur d'`errno` et la valeur de retour sont les deux `EINVAL`, indiquant un paramètre non valide.  Dans certains cas, le code d'erreur plus spécifique est retourné, par exemple `EBADF` pour un mauvais pointeur de fichier transmis en tant que paramètre.  Pour plus d'informations sur errno, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Voir aussi  
 [Fonctionnalités de sécurité dans le CRT](../c-runtime-library/security-features-in-the-crt.md)   
 [Fonctions de bibliothèque CRT](../c-runtime-library/crt-library-features.md)