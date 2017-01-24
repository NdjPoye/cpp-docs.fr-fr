---
title: "Erreur des outils &#201;diteur de liens LNK1000 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1000"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1000"
ms.assetid: 86421b9a-460a-4285-8dce-9b8257d78122
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK1000
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

erreur inconnue ; consultez la documentation du support technique  
  
 Notez les circonstances de l'erreur, essayez de cerner le problème et de créer un exemple de test reproductible, puis consultez `Microsoft Product Support Services`.  Pour plus d'informations sur comment élucider et reporter ces erreurs, consultez [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;134650](http://support.microsoft.com/default.aspx?scid=kb;en-us;134650).  
  
 Cette erreur peut être générée si vous mélangez des fichiers d'en\-tête standard \(par exemple, dos.h\) avec vos propres fichiers.  Incluez \(`#include`\) d'abord les fichiers d'en\-tête standard, puis vos propres fichiers d'en\-tête.