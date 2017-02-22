---
title: "Erreur irr&#233;cup&#233;rable C1084 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1084"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1084"
ms.assetid: b2f273ef-3a14-4d5f-8ce0-7a11a0388fe6
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur irr&#233;cup&#233;rable C1084
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Impossible de lire le fichier 'TypeFichier' : 'fichier' : message  
  
 Cette erreur résulte généralement de l'échec d'un appel à une API système interne effectué par le compilateur.  Le message qui s'affiche quand cette erreur survient est souvent généré par [\_wcserror\_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md) ou [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351.aspx).  
  
 La procédure ci\-dessous peut aider à résoudre l'erreur C1084 :  
  
-   Assurez\-vous que le fichier spécifié existe.  
  
-   Assurez\-vous que les autorisations appropriées sont définies afin de pouvoir accéder au fichier spécifié.  
  
-   Assurez\-vous que la syntaxe de ligne de commande adhère aux règles stipulées sous [Syntaxe de la ligne de commande du compilateur](../../build/reference/compiler-command-line-syntax.md).  
  
-   Assurez\-vous que les variables d'environnement **TMP** et **TEMP** sont correctement définies, ainsi que les autorisations appropriées permettant d'accéder aux répertoires auxquels ces variables d'environnement font référence.  Assurez\-vous également que les lecteurs référencés par les variables d'environnement **TMP** et **TEMP** contiennent une quantité adéquate d'espace disponible.  
  
-   Si le message indique « numéro de fichier incorrect », le fichier spécifié était peut\-être en cours de fermeture au premier plan alors que la compilation se déroulait en arrière\-plan.  
  
 Après avoir effectué les diagnostics ci\-dessus, effectuez un nettoyage de build.