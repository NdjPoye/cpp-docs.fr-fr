---
title: "Avertissement du compilateur C4394 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4394"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4394"
ms.assetid: 5de94de0-17e3-4e7c-92f4-5c3c1b825120
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Avertissement du compilateur C4394
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : un symbole par appdomain ne doit pas être marqué avec \_\_declspec\(dllexport\)  
  
 Une fonction marquée avec le modificateur [appdomain](../../cpp/appdomain.md) `__declspec` est compilée en code MSIL \(et non natif\), et les tables d'exportation \(modificateur [export](../../windows/export.md) `__declspec`\) ne sont pas prises en charge pour les fonctions managées.  
  
 Déclarez une fonction managée pour avoir un accès public.  Pour plus d'informations, consultez [Visibilité du type](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) et [Visibilité de membre](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility).  
  
 C4394 est toujours émis en tant qu'erreur.  Vous pouvez désactiver cet avertissement avec `#pragma warning` ou **\/wd** ; consultez [warning](../../preprocessor/warning.md) ou [\/w, \/Wn, \/WX, \/Wall, \/wln, \/wdn, \/wen, \/won \(Niveau d'avertissement\)](../../build/reference/compiler-option-warning-level.md) pour plus d'informations.  
  
## Exemple  
 L'exemple suivant génère l'erreur C4394 :  
  
```  
// C4394.cpp  
// compile with: /clr /c  
__declspec(dllexport) __declspec(appdomain) int g1 = 0;   // C4394  
__declspec(dllexport) int g2 = 0;   // OK  
```