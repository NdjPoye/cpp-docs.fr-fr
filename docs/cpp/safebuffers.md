---
title: safebuffers | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- safebuffers_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword (C++), safebuffers
- safebuffers __declspec keyword
ms.assetid: 0b0dce14-4523-44d2-8070-5dd0fdabc618
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fbfc9317b5ed7c63e9c70b081c3f241b86a65e5f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="safebuffers"></a>safebuffers
**Section spécifique à Microsoft**  
  
 Indique au compilateur de ne pas insérer de vérifications de sécurité de dépassement de mémoire tampon pour une fonction.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
__declspec( safebuffers )  
```  
  
## <a name="remarks"></a>Notes  
 Le **/GS** option du compilateur, le compilateur tester les dépassements de mémoire tampon en insérant des vérifications de sécurité sur la pile. Les types de structures de données qui sont éligibles pour les vérifications de sécurité sont décrits dans [/GS (vérification de la sécurité de la mémoire tampon)](../build/reference/gs-buffer-security-check.md). Pour plus d’informations sur la détection de dépassement de mémoire tampon, consultez [du compilateur sécurité Contrôles approfondis de](http://go.microsoft.com/fwlink/p/?linkid=7260) sur le site Web MSDN.  
  
 Une revue manuelle du code par un expert ou une analyse externe peut déterminer qu’une fonction est protégée contre un dépassement de mémoire tampon. Dans ce cas, vous pouvez supprimer des contrôles de sécurité pour une fonction en appliquant la `__declspec(safebuffers)` mot clé à la déclaration de fonction.  
  
> [!CAUTION]
>  Les vérifications de sécurité de la mémoire tampon assurent une protection importante et ont un impact négligeable sur les performances. Par conséquent, nous vous recommandons de ne pas les supprimer, sauf dans la rare éventualité où les performances d'une fonction est un problème critique et où la fonction est réputée pour être sécurisée.  
  
## <a name="inline-functions"></a>Fonctions inline  
 A *fonction principale* peut utiliser un [incorporation (inlining)](inline-functions-cpp.md) mot clé permettant d’insérer une copie d’un *fonction secondaire*. Si le `__declspec(safebuffers)` (mot clé) est appliqué à une fonction, la détection de dépassement de mémoire tampon est supprimée pour cette fonction. Toutefois, incorporation affecte le `__declspec(safebuffers)` mot clé comme suit.  
  
 Supposons que la **/GS** option du compilateur est spécifiée pour les deux fonctions, mais la fonction principale spécifie les `__declspec(safebuffers)` (mot clé). Les structures de données présentes dans la fonction secondaire lui permettent de faire l'objet de vérifications de sécurité, et la fonction ne supprime pas ces vérifications. Dans ce cas :  
  
-   Spécifiez le [__forceinline](inline-functions-cpp.md) mot clé dans la fonction secondaire pour forcer le compilateur à incorporer cette fonction indépendamment des optimisations du compilateur.  
  
-   Étant donné que la fonction secondaire est éligible à des vérifications de sécurité, les vérifications de sécurité sont également appliquées à la fonction principale bien qu’elle spécifie le `__declspec(safebuffers)` (mot clé).  
  
## <a name="example"></a>Exemple  
 Le code suivant montre comment utiliser le `__declspec(safebuffers)` (mot clé).  
  
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
  
## <a name="see-also"></a>Voir aussi  
 [__declspec](../cpp/declspec.md)   
 [Mots clés](../cpp/keywords-cpp.md)   
 [inline, __inline, \__forceinline](inline-functions-cpp.md)   
 [strict_gs_check](../preprocessor/strict-gs-check.md)