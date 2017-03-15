---
title: "Erreur du compilateur C3872 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3872"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3872"
ms.assetid: 519e95be-5641-40cc-894c-da4819506604
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Erreur du compilateur C3872
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

’char’ : ce caractère n’est pas autorisé dans un identificateur  
  
 Le compilateur C\+\+ suit la norme C\+\+11 sur les caractères autorisés dans un identificateur. Seules certaines plages de caractères et certains noms de caractères universels sont autorisés dans un identificateur. Des restrictions supplémentaires s’appliquent au caractère initial d’un identificateur. Pour plus d’informations et pour obtenir la liste des caractères et des plages de noms de caractères universels autorisés, consultez [Identificateurs C\+\+](../../cpp/identifiers-cpp.md).  
  
 La plage des caractères autorisés dans un identificateur est moins restrictive durant la compilation du code C\+\+\/CLI. Les identificateurs contenus dans du code compilé à l’aide de \/clr doivent suivre la [norme ECMA\-335 : Common Language Infrastructure \(CLI\)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).  
  
 L’exemple suivant génère l’erreur C3872 :  
  
```  
// C3872.cpp int main() { int abc_\u0040;   // C3872, U+0040 is in base char set int abc_\u3001;   // C3872, U+3001 is not in allowed range int \u30A2_abc_\u3042;   // OK, UCNs in allowed range }  
```