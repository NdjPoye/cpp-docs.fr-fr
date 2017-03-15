---
title: "Erreur du compilateur C2893 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2893"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2893"
ms.assetid: ec0cbe43-005d-45da-8742-aaeb9b81d28e
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Erreur du compilateur C2893
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La spécialisation du modèle de fonction 'nom de modèle' a échoué  
  
 Le compilateur n'a pas réussi à spécialiser un modèle de fonction.  Il peut exister plusieurs causes pour cette erreur.  
  
 En général, l'erreur C2893 peut être résolue en vérifiant la signature de la fonction et en vous assurant que vous pouvez instancier chaque type.  
  
## Exemple  
 L'erreur C2893 se produit parce que le paramètre de modèle `T` de `f` est déduit comme étant `std::map<int,int>`, mais `std::map<int,int>` n'a aucun `data_type` membre \(`T::data_type` ne peut pas être instancié avec `T = std::map<int,int>`\).  L'exemple suivant génère l'erreur C2893 :  
  
```  
// C2893.cpp  
// compile with: /c /EHsc  
#include<map>  
using namespace std;  
class MyClass {};  
  
template<class T>   
inline typename T::data_type  
// try the following line instead  
// inline typename  T::mapped_type  
f(T const& p1, MyClass const& p2);  
  
template<class T>  
void bar(T const& p1) {  
    MyClass r;  
    f(p1,r);   // C2893  
}  
  
int main() {  
   map<int,int> m;  
   bar(m);  
}  
```