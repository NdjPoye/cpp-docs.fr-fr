---
title: "Surcharge de l&#39;op&#233;rateur &lt;&lt; pour vos propres classes | Microsoft Docs"
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
helpviewer_keywords: 
  - "opérateur <<, surcharge pour vos propres classes"
  - "operator<<, surcharge pour vos propres classes"
ms.assetid: ad1d2c49-d84e-48a8-9c09-121f28b10bf0
caps.latest.revision: 12
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Surcharge de l&#39;op&#233;rateur &lt;&lt; pour vos propres classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les flux de sortie utilisent l'opérateur insert \(`<<`\) pour les types standard.  Vous pouvez également de surcharger l'opérateur d'`<<` pour vos propres classes.  
  
## Exemple  
 L'exemple de fonction d'`write` indiquée l'utilisation d'une structure d'`Date`.  Une date est un candidat idéal pour la classe actuelle c \+\+ dans laquelle les membres de données \(mois, jour, et année\) sont masqués de la vue.  Un flux de sortie est la destination logique pour afficher une telle structure.  Ce code affiche une date à l'objet d'`cout` :  
  
```  
Date dt( 1, 2, 92 );  
cout << dt;  
```  
  
 Pour obtenir `cout` de recevoir un objet d'`Date` après l'opérateur insert, surchargez l'opérateur d'insertion pour identifier un objet d'`ostream` à gauche et un `Date` à droite.  La fonction surchargée d'opérateur `<<` doit être déclarée comme une fonction friend de la classe `Date` ce qui peut accéder à des données privées dans un objet d'`Date`.  
  
```  
// overload_date.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
class Date  
{  
    int mo, da, yr;  
public:  
    Date(int m, int d, int y)  
    {  
        mo = m; da = d; yr = y;  
    }  
    friend ostream& operator<<(ostream& os, const Date& dt);  
};  
  
ostream& operator<<(ostream& os, const Date& dt)  
{  
    os << dt.mo << '/' << dt.da << '/' << dt.yr;  
    return os;  
}  
  
int main()  
{  
    Date dt(5, 6, 92);  
    cout << dt;  
}  
```  
  
  **5\/6\/92**   
## Notes  
 L'opérateur surchargé retourne une référence à l'objet d'origine des `ostream`, ce qui signifie que vous pouvez combiner des insertions :  
  
```  
cout << "The date is" << dt << flush;  
```  
  
## Voir aussi  
 [Flux de sortie](../standard-library/output-streams.md)