---
title: "Erreur des outils &#201;diteur de liens LNK2033 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2033"
ms.assetid: d61db467-9328-4788-bf54-e2a20537f13f
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# Erreur des outils &#201;diteur de liens LNK2033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

jeton typeref non résolu \(jeton\) pour 'type'  
  
 Un type ne possède pas de définition dans les métadonnées MSIL.  
  
 L'erreur LNK2033 peut se produire lors de la compilation avec **\/clr:safe** et s'il n'existe qu'une déclaration anticipée pour un type contenu dans un module MSIL, où le type est référencé dans le module MSIL.  
  
 Le type doit être défini sous **\/clr:safe**.  
  
 Pour plus d'informations, consultez [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur LNK2033.  
  
```  
// LNK2033.cpp  
// compile with: /clr:safe  
// LNK2033 expected  
ref class A;  
ref class B {};  
  
int main() {  
   A ^ aa = nullptr;  
   B ^ bb = nullptr;   // OK  
};  
```