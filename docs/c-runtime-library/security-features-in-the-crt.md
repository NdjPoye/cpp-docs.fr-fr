---
title: "Fonctionnalit&#233;s de s&#233;curit&#233; dans le CRT | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_CRT_SECURE_NO_DEPRECATE"
  - "_CRT_NONSTDC_NO_WARNINGS"
  - "_CRT_SECURE_NO_WARNINGS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CRT_NONSTDC_NO_DEPRECATE"
  - "_CRT_NONSTDC_NO_WARNINGS"
  - "_CRT_SECURE_NO_DEPRECATE"
  - "_CRT_SECURE_NO_WARNINGS"
  - "dépassements de mémoire tampon"
  - "mémoires tampons (C++), dépassements de mémoire tampon"
  - "CRT, améliorations de sécurité"
  - "CRT_NONSTDC_NO_DEPRECATE"
  - "CRT_NONSTDC_NO_WARNINGS"
  - "CRT_SECURE_NO_DEPRECATE"
  - "CRT_SECURE_NO_WARNINGS"
  - "avertissements de désapprobation (liés à la sécurité)"
  - "avertissements de désapprobation (liés à la sécurité), désactiver"
  - "paramètres (C++), validation"
  - "sécurité (CRT)"
  - "avertissements de désapprobation de sécurité (C++)"
  - "sécurité CRT améliorée"
ms.assetid: d9568b08-9514-49cd-b3dc-2454ded195a3
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# Fonctionnalit&#233;s de s&#233;curit&#233; dans le CRT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

De nombreuses anciennes fonctions CRT ont de nouvelles moutures plus sécurisées.  Si une fonction sécurisée existe, la version antérieure et moins sécurisée est marquée comme déconseillée et la nouvelle version a le suffixe `_s` \(« sécurisée »\).  
  
 Dans ce contexte, « est déconseillé » signifie que l'utilisation d'une fonction n'est pas recommandée ; il n'indique pas si la suppression de la fonction du CRT est plannifiée.  
  
 Les fonctions sécurisées n'empêchent pas ou ne corrige pas les erreurs de sécurité ; en revanche, elles décèlent des erreurs lorsqu'elles se produisent.  Ils effectuent les contrôles supplémentaires pour des conditions d'erreur, et en cas d'erreur, ils appellent un gestionnaire d'erreurs \(consultez [Validation de paramètre](../c-runtime-library/parameter-validation.md)\).  
  
 Par exemple, la fonction `strcpy` n'a aucun moyen de déterminer si la chaîne qu'il copie est trop grande pour son tampon de destination.  Toutefois, son équivalent sécurisé, `strcpy_s`, prend la taille de la mémoire tampon en tant que paramètre, ce qui peut déterminer si un dépassement de mémoire tampon se produira.  Si vous utilisez `strcpy_s` pour copier onze caractères dans une mémoire tampon de dix\- caractère, il s'agit d'une erreur de votre part ; `strcpy_s` ne peut pas corriger l'erreur, mais elle peut la détecter et vous en avertir en appelant le gestionnaire de paramètre non valide.  
  
## Suppression des avertissements d'abandon  
 Il existe plusieurs façons d'éliminer les avertissements d'abandon des fonctions anciennes ou moins sécurisées.  Le plus simple est simplement de définir `_CRT_SECURE_NO_WARNINGS` ou utilisez le pragma [warning](../preprocessor/warning.md).  L'option désactive les avertissements d'abandon, mais naturellement les problèmes de sécurité, qui provoquaient les avertissements existent toujours.  Il est préférable de laisser les avertissements d'abandon activés et de tirer parti des nouvelles fonctionnalités de sécurité CRT.  
  
 En C\+\+, la méthode la plus simple pour le faire et d'utiliser [Sécuriser les surcharges de modèle](../c-runtime-library/secure-template-overloads.md), qui dans de nombreux cas élimine les avertissements d'abandon en remplaçant des appels aux fonctions déconseillées par des appels aux nouvelles versions sécurisées de ces fonctions.  Par exemple, considérez l'appel déconseillé à `strcpy`:  
  
```  
char szBuf[10];   
strcpy(szBuf, "test"); // warning: deprecated   
```  
  
 Définir `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` comme 1 supprime l'avertissement en modifiant l'appel `strcpy` à `strcpy_s`, ce qui empêche les dépassements de mémoire tampon.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../c-runtime-library/secure-template-overloads.md).  
  
 Pour les fonctions déconseillées sans surcharges de modèle, vous devriez envisager de mettre à jour manuellement votre code pour utiliser les versions sécurisées.  
  
 Une autre source d'avertissements d'abandon, non liée à la sécurité, sont les fonctions de POSIX.  Remplacez les noms des fonctions de POSIX par leurs équivalents standard \(par exemple, remplacez [accès](../c-runtime-library/reference/access-crt.md) par [\_access](../c-runtime-library/reference/access-waccess.md)\), ou désactivez les avertissements d'abandon POSIX en définissant `_CRT_NONSTDC_NO_WARNINGS`.  Pour plus d'informations, consultez [Deprecated CRT Functions](http://msdn.microsoft.com/fr-fr/7e259932-c6c8-4c1a-9637-639e591681a5).  
  
## Ressources de sécurité supplémentaires  
 Voici quelques\-unes de ces fonctionnalités :  
  
-   `Parameter Validation`.  Les paramètres transmis aux fonctions CRT sont validés, dans aussi bien les fonctions sécurisées que dans de nombreuses versions preexistentes de ces fonctions.  Ces validations incluent :  
  
    -   Vérifier si les valeurs `NULL` sont transmises aux fonctions.  
  
    -   Vérification des valeurs énumérées pour validation.  
  
    -   Vérifier que les valeurs intégrales sont dans des intervalles valides.  
  
-   Pour plus d'informations, consultez [Validation de paramètre](../c-runtime-library/parameter-validation.md).  
  
-   Un gestionnaire pour les paramètres non valides est également disponible au développeur.  Lors de la rencontre avec un paramètre non valide, au lieu de déclarer et de quitter l'application, le CRT fournit un moyen de vérifier ces problèmes avec la fonction[\_set\_invalid\_parameter\_handler, \_set\_thread\_local\_invalid\_parameter\_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) .  
  
-   `Sized Buffers`.  Les fonctions sécurisées requièrent que la taille de mémoire tampon soit passée à n'importe quelle fonction qui écrit dans une mémoire tampon.  Les versions sécurisées valide que la mémoire tampon soit assez large avant de l'écrire, ce qui aide à empecher des dangereuses erreurs de mémoire tampon, qui pourraient permettre à des codes de mauvaise intentions de s'executer.  Ces fonctions retournent généralement un type de code erreur`errno`et appellent le gestionnaire de paramètre non valide si la taille de la mémoire tampon est trop petite.  Les fonctions, qui sont lues depuit les mémoires tampons d'entrée, telles que `gets`, ont des versions sécurisées qui exigent que vous spécifiez une taille maximale.  
  
-   `Null termination`.  Certaines fonctions qui laissent des chaines potentiellement non terminées inchangées ont des versions sécurisées qui garantissent que les chaînes sont correctement terminées \(avec le caractère NULL\).  
  
-   `Enhanced error reporting`.  Ces fonctions sécurisées retournent des codes d'erreur avec plus d'information sur les erreurs, que ce qui était disponible avec les fonctions preexistentes.  Les fonctions sécurisées et beaucoup de fonctions préexistentes définissent maintenant `errno`et retournent souvent un type de code `errno` également, pour garantir un meilleur rapport d'erreurs.  
  
-   `Filesystem security`.  Les fichiers sécurisés I\/O APIs permettent un accès sécurisé aux fichiers par défaut.  
  
-   `Windows security`.  Les API de traitement sécurisées appliquent les stratégies de sécurité et permettent aux listes de contrôle d'accès d'etre spécifiées.  
  
-   `Format string syntax checking`.  Les chaînes non valides sont détectées, par exemple, en utilisant les caractères de champs de type incorrect dans les chaines de format `printf`.  
  
## Voir aussi  
 [Validation de paramètre](../c-runtime-library/parameter-validation.md)   
 [Sécuriser les surcharges de modèle](../c-runtime-library/secure-template-overloads.md)   
 [Fonctions de bibliothèque CRT](../c-runtime-library/crt-library-features.md)