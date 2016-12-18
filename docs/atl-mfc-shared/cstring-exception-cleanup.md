---
title: "CString Exception Cleanup | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CString objects, exceptions"
  - "gestion des exceptions, cleanup code"
ms.assetid: 28b9ce70-be63-4a0d-92a8-44bbfbc95e83
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CString Exception Cleanup
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans les versions antérieures de MFC, il est important que vous nettoyiez après l'utilisation d'objets de [CString](../atl-mfc-shared/reference/cstringt-class.md) .  Avec la version 3,0 de MFC et le nettoyage ultérieurement et explicite n'est plus nécessaire.  
  
 Sous le mécanisme de gestion des exceptions C\+\+ que MFC utilise maintenant, vous n'avez pas à vous préoccuper de nettoyage après une exception.  Pour une description de la façon dont C\+\+ « déroule » pile après qu'une exception est interceptée, consultez [le test, le Catch, et les instructions throw](../cpp/try-throw-and-catch-statements-cpp.md).  Même si vous utilisez MFC **TRY**\/macros de**collecteur** au lieu des mots clés **try** et **collecteur**C\+\+, MFC utilise le mécanisme d'exceptions C\+\+ sous, vous n'avez pas toujours besoin de nettoyage explicite.  
  
## Voir aussi  
 [Chaînes](../atl-mfc-shared/strings-atl-mfc.md)   
 [Gestion des exceptions](../mfc/exception-handling-in-mfc.md)