---
title: "Avertissement du compilateur (niveau 1) C4743 | Microsoft Docs"
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
  - "C4743"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4743"
ms.assetid: 2ee76ea3-77f3-4c2f-9a57-0751823c89fd
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4743
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'*type*' a une taille différente dans '*file1*' et '*file2*' : *number* et *number* octets  
  
 Une variable externe référencée ou définie par l'utilisateur dans deux fichiers possède des types différents dans ces fichiers, et le compilateur a déterminé que la taille de la variable contenue dans *file1* diffère de la taille de la variable contenue dans *file2*.  
  
 Cet avertissement peut être émis pour C\+\+ dans des cas graves.  Si vous déclarez les mêmes types avec le même nom dans deux fichiers différents, si ces déclarations contiennent des fonctions virtuelles, et si les déclarations ne sont pas identiques, le compilateur peut émettre l'avertissement C4744 pour les tables de fonctions virtuelles.  L'avertissement se produit parce qu'il existe deux tables de fonctions virtuelles de taille différente pour le même type, et que l'éditeur de liens doit en choisir une afin de l'incorporer dans le fichier exécutable.  Il est possible que votre programme appelle ensuite une fonction virtuelle incorrecte.  
  
 Pour résoudre cet avertissement, utilisez la même définition de type ou des noms différents pour les types ou les variables.  
  
## Exemple  
 Cet exemple contient une définition du type.  
  
```  
// C4743a.cpp  
// compile with: /c  
class C {  
public:  
    virtual void f1(void);  
    virtual void f2(void);  
    virtual void f3(void);  
};  
  
void C::f1(void) {}  
void C::f2(void) {}  
void C::f3(void) {}  
C q;  
```  
  
## Exemple  
 L'exemple suivant génère l'erreur C4743.  
  
```  
// C4743b.cpp  
// compile with: C4743a.cpp /W1 /GL /O2  
// C4743 expected  
class C {  
public:  
    virtual void f1(void);  
    virtual void f2(void);  
    virtual void f3(void);  
    virtual void f4(void);  
    virtual void f5(void);  
};  
  
void C::f4(void) {}  
void C::f5(void) {}  
C x;  
  
int main() {}   
```