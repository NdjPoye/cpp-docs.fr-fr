---
title: "safebuffers | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "safebuffers"
  - "safebuffers_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec (mot clé) (C++), safebuffers"
  - "safebuffers __declspec (mot clé)"
ms.assetid: 0b0dce14-4523-44d2-8070-5dd0fdabc618
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# safebuffers
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Indique au compilateur de ne pas insérer de vérifications de sécurité de dépassement de mémoire tampon pour une fonction.  
  
## Syntaxe  
  
```  
__declspec( safebuffers )  
```  
  
## Notes  
 L'option **\/GS** du compilateur oblige ce dernier à effectuer des tests pour détecter d'éventuels dépassements de mémoire tampon en insérant des vérifications de sécurité sur la pile.  Les types de structures de données pouvant faire l'objet de vérifications de sécurité sont décrites dans [\/GS \(vérification de la sécurité des mémoires tampons\)](../build/reference/gs-buffer-security-check.md).  Pour plus d'informations sur la détection des dépassements de mémoire tampon, consultez [Contrôles approfondis de la sécurité du compilateur](http://go.microsoft.com/fwlink/?linkid=7260) sur le site Web MSDN.  
  
 Une révision manuelle du code par un expert ou une analyse externe peut déterminer qu'une fonction est protégée contre un dépassement de mémoire tampon.  Dans ce cas, vous pouvez supprimer les vérifications de sécurité pour une fonction en appliquant le mot clé \_\_`declspec(safebuffers)` à la déclaration de fonction.  
  
> [!CAUTION]
>  Les vérifications de sécurité de la mémoire tampon assurent une protection importante et ont un impact négligeable sur les performances.  Par conséquent, nous vous recommandons de ne pas les supprimer, sauf dans la rare éventualité où les performances d'une fonction est un problème critique et où la fonction est réputée pour être sécurisée.  
  
## Fonctions inline  
 Une *fonction principale* peut utiliser un mot clé d'[incorporation](../misc/inline-inline-forceinline.md) pour insérer une copie d'une *fonction secondaire*.  Si le mot clé \_\_`declspec(safebuffers)` est appliqué à une fonction, la détection des dépassements de mémoire tampon est supprimée pour cette fonction.  Toutefois, l'incorporation affecte le mot clé \_\_`declspec(safebuffers)` des manières suivantes.  
  
 Supposons que l'option **\/GS** du compilateur est spécifiée pour les deux fonctions, mais que la fonction principale spécifie le mot clé \_\_`declspec(safebuffers)` .  Les structures de données présentes dans la fonction secondaire lui permettent de faire l'objet de vérifications de sécurité, et la fonction ne supprime pas ces vérifications.  Dans ce cas :  
  
-   Spécifiez le mot clé [\_\_forceinline](../misc/inline-inline-forceinline.md) sur la fonction secondaire pour forcer le compilateur à incorporer \(inline\) cette fonction indépendamment des optimisations du compilateur.  
  
-   Comme la fonction secondaire peut faire l'objet de vérifications de sécurité, ces dernières sont également appliquées à la fonction principale bien qu'elle spécifie le mot clé \_\_`declspec(safebuffers)` .  
  
## Exemple  
 Le code suivant montre comment utiliser le mot clé \_\_`declspec(safebuffers)` .  
  
```  
// compile with: /c /GS  
typedef struct {  
    int x[20];  
} BUFFER;  
static int checkBuffers() {  
    BUFFER cb;  
    // Use the buffer...  
    return 0;  
};  
static __declspec(safebuffers)   
    int noCheckBuffers() {  
    BUFFER ncb;  
    // Use the buffer...  
    return 0;  
}  
int wmain() {  
    checkBuffers();  
    noCheckBuffers();  
    return 0;  
}  
```  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_\_declspec](../cpp/declspec.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [inline, \_\_inline, \_\_forceinline](../misc/inline-inline-forceinline.md)   
 [strict\_gs\_check](../preprocessor/strict-gs-check.md)