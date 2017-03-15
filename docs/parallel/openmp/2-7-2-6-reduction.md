---
title: "2.7.2.6 reduction | Microsoft Docs"
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
ms.assetid: e7630a15-2978-4dbe-a29b-3a46371a0151
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2.6 reduction
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette clause effectue une réduction sur les variables scalaires qui s'affichent dans *la variable\-liste*, avec l'opérateur op.  La syntaxe de la clause d' `reduction` est la suivante :  
  
```  
  
reduction(  
op  
:  
variable-list  
)  
  
```  
  
 Une réduction est généralement spécifiée pour une instruction avec une des formes suivantes :  
  
```  
  
        x     =  x     op     expr  
x     binop=  expr  
x     =  expr     op     x            (except for subtraction)  
x++  
++x  
x--  
--x  
```  
  
 où :  
  
 *x*  
 L'une des variables de réduction spécifiées dans `list`.  
  
 *variable\-liste*  
 Une liste avec la virgule comme séparateur des variables scalaires de réduction.  
  
 *expr*  
 une expression avec le type scalaire qui ne référence pas le *X.*  
  
 `op`  
 Pas d'opérateur surchargé mais un de type \+, \*, \- &, ^, &#124; &&, ou &#124;&#124;.  
  
 `binop`  
 Pas d'opérateur surchargé mais un de type \+, \*, \- &, ^, ou &#124;.  
  
 Voici un exemple de la clause d' `reduction` :  
  
```  
#pragma omp parallel for reduction(+: a, y) reduction(||: am)  
for (i=0; i<n; i++) {  
   a += b[i];  
   y = sum(y, c[i]);  
   am = am || b[i] == c[i];  
}  
```  
  
 Comme indiqué dans l'exemple, un opérateur peut être masqué dans un appel de fonction.  L'utilisateur doit veiller que l'opérateur spécifié dans la clause d' `reduction` correspond à l'opération de réduction.  
  
 Bien que l'opérande de droite de &#124;&#124; l'opérateur n'a aucun effet secondaire dans cet exemple, ils sont autorisés, mais doivent être utilisés avec prudence.  Dans ce contexte, un effet secondaire qui est garanti ne pas se produire pendant l'exécution séquentielle de la boucle peut se produire pendant l'exécution parallèle.  Cette différence peut se produire parce que l'ordre d'exécution des itérations est indéterminé.  
  
 L'opérateur est utilisé pour déterminer la valeur initiale de toutes les variables privées utilisées par le compilateur pour la réduction et pour déterminer l'opérateur de finalisation.  Spécifier l'opérateur permet explicitement à l'instruction de réduction pour être à l'extérieur de l'étendue lexicale de l'élément.  Plusieurs clauses d' `reduction` peuvent être spécifiées sur la directive, mais une variable peut apparaître dans au plus une clause d' `reduction` pour cette directive.  
  
 une copie privée de chaque variable dans la variable\- *liste* est créée, une pour chaque thread, comme si la clause d' `private` avait été utilisée.  La copie privée est initialisée en fonction de l'opérateur \(consultez le tableau suivant\).  
  
 À la fin de la zone pour laquelle la clause d' `reduction` a été spécifiée, l'objet d'origine est mis à jour pour refléter le résultat de la combinaison de sa valeur d'origine avec la valeur finale de chacune des copies privées à l'aide de l'opérateur spécifié.  Les opérateurs sont tous de réduction associatifs \(à l'exception de la soustraction\), et le compilateur peut librement rassocier le calcul de la dernière valeur.  \(Les résultats partiels d'une réduction de soustraction sont ajoutés pour former la valeur finale.\)  
  
 La valeur de l'objet d'origine devient indéterminée lorsque le premier thread atteint la clause conteneur et reste donc jusqu'à ce que le calcul de réduction terminé.  Normalement, le calcul est interrompue à la fin de l'élément ; toutefois, si la clause d' `reduction` est utilisée dans un élément auquel `nowait` est également appliqué, la valeur de l'objet d'origine reste indéterminée jusqu'à ce qu'une synchronisation de cloisonnement effectuée pour garantir que tous les threads ont terminé la clause d' `reduction` .  
  
 Le tableau suivant répertorie les opérateurs qui sont valides et leurs valeurs canoniques d'initialisation.  La valeur réelle d'initialisation est compatible avec le type de données de la variable de réduction.  
  
|Opérateur|Initialisation|  
|---------------|--------------------|  
|\+|0|  
|\*|1|  
|\-|0|  
|&|~0|  
|&#124;|0|  
|^|0|  
|&&|1|  
|&#124;&#124;|0|  
  
 Les restrictions sur la clause d' `reduction` sont les suivantes :  
  
-   Le type des variables dans la clause d' `reduction` doit être valide pour l'opérateur de réduction mais les types pointeur et les types référence ne sont pas autorisés.  
  
-   Une variable spécifiée dans la clause d' `reduction` ne doit pas être **const**\- qualifié.  
  
-   Les variables qui sont privées dans une région parallèle ou qui apparaissent dans la clause d' `reduction` d'une directive de **parallèle** ne peuvent pas être spécifiées dans une clause d' `reduction` sur une directive de partage du travail qui se lie à l'élément parallèle.  
  
    ```  
    #pragma omp parallel private(y)  
    { /* ERROR - private variable y cannot be specified  
                 in a reduction clause */  
       #pragma omp for reduction(+: y)  
       for (i=0; i<n; i++)  
          y += b[i];  
    }  
  
    /* ERROR - variable x cannot be specified in both  
               a shared and a reduction clause */  
    #pragma omp parallel for shared(x) reduction(+: x)  
    ```