---
title: "Erreur des outils &#201;diteur de liens LNK2031 | Microsoft Docs"
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
  - "LNK2031"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2031"
ms.assetid: 18ed4b6e-3e75-443c-bbd8-2f6030dc89ee
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK2031
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible de générer p\/invoke pour déclaration\_fonction nom\_décoré ; convention d'appel manquante dans les métadonnées  
  
 Lors d'une tentative d'importation d'une fonction native dans une image pure, n'oubliez pas que les conventions d'appel implicites diffèrent entre les compilations natives et pures.  Pour plus d'informations sur les images purs, consultez [Code pur et vérifiable](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
## Exemple  
 Cet exemple de code génère un composant avec une fonction native exportée dont la convention d'appel est implicitement [\_\_cdecl](../../cpp/cdecl.md).  
  
```  
// LNK2031.cpp  
// compile with: /LD  
extern "C" {  
   __declspec(dllexport) int func() { return 3; }  
};  
```  
  
## Exemple  
 L'exemple suivant crée un client pure qui utilise la fonction native.  Toutefois, la convention d'appel sous **\/clr:pure** est [\_\_clrcall](../../cpp/clrcall.md).  L'exemple suivant génère l'erreur LNK2031.  
  
```  
// LNK2031_b.cpp  
// compile with: /clr:pure LNK2031.lib  
// LNK2031 expected  
extern "C" int func();  
  
int main() {  
   return func();  
}  
```  
  
## Exemple  
 L'exemple suivant montre comment utiliser la fonction native à partir d'une image pure.  Notez le spécificateur de la convention d'appel **\_\_cdecl** explicite.  
  
```  
// LNK2031_c.cpp  
// compile with: /clr:pure LNK2031.lib  
extern "C" int __cdecl func();  
  
int main() {  
   return func();  
}  
```