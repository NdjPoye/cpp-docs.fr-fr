---
title: "2.4.1 for Construct | Microsoft Docs"
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
ms.assetid: 27d2cbce-786b-4819-91d3-d55b2cc57a5e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.4.1 for Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La directive de **pour** identifie un élément itératif de partage de travail qui spécifie que les itérations de la boucle associée seront exécutées en parallèle.  Les itérations de la boucle de **pour** sont distribuées sur les threads qui existent déjà dans l'équipe exécutant l'élément parallèle auquel il est lié.  La syntaxe de l'élément de **pour** est la suivante :  
  
```  
#pragma omp for [clause[[,] clause] ... ] new-line  
   for-loop  
```  
  
 La clause est l'une des opérations suivantes :  
  
 *variable\-liste* **\)**de**privé \(**  
  
 *variable\-liste* **\)**de**firstprivate \(**  
  
 *variable\-liste* **\)**d'**elle \(**  
  
 *variable\-liste* **\)**de**Numéro de téléphone :** d'*opérateur de***réduction \(**  
  
 **dimensionné**  
  
 *type*de**planifier \(**\[,\]**\)** *chunk\_size*  
  
 **nowait**  
  
 Les restrictions directives d'emplacements de **pour** à la structure de **pour** correspondant bouclent.  spécifiquement, la boucle correspondante de **pour** doit avoir la forme canonique :  
  
 *var b logique\-op*de**pour \(***init\-expr***;**; *augmentation\-expr***\)**  
  
 *init\-expr*  
 Une des valeurs suivantes :  
  
 *var* \= *livre*  
  
 *entier\-type var* \= *livre*  
  
 *augmentation\-expr*  
 Une des valeurs suivantes :  
  
 \+\+var  
  
 *var* \+\+  
  
 \-\- *var*  
  
 *var* \-\-  
  
 *augmentation* *du var* \+\=  
  
 *var* \- \= *augmentez*  
  
 *" var "* \= *" var "* \+ *accru*  
  
 *var* \= *accru* \+ *var*  
  
 *var* \= *var* \- *incr*  
  
 *var*  
 une variable d'entier signé.  Si cette variable devrait être partagée, il est implicitement rendue privée pour la durée de **pour**.  Cette variable ne doit pas être modifiée dans le corps de l'instruction de **pour** .  Sauf si la variable est **elle**spécifié, sa valeur après la boucle soit indéterminée.  
  
 *logique\-op*  
 Une des valeurs suivantes :  
  
 \<  
  
 \<\=  
  
 \>  
  
 \>\=  
  
 *livre*, *b*, et *augmentation*  
 Expressions d'entiers invariantes de boucle.  Il n'existe aucune synchronisation pendant l'évaluation de ces expressions.  Par conséquent, tous les effets secondaires évalués produisent des résultats indéterminés.  
  
 notez que la forme canonique permet le nombre d'itérations de boucle à calculer sur l'entrée à la boucle.  Ce calcul est exécuté avec les valeurs du type *de var*, après les promotions intégrales.  en particulier, si valeur de *b* \- *livre* \+ *accru* ne peut pas être représentée dans ce type, le résultat est indéterminé.  De plus, si *logique\-op* est \< ou \<\= ensuite *augmentation\-expr* doit provoquer *le var* à l'augmentation sur chaque itération de la boucle.  Si *logique\-op* est \> ou \>\= ensuite *augmentation\-expr* doit provoquer *le var* la baisse sur chaque itération de la boucle.  
  
 La clause de **planification** spécifie comment les itérations de la boucle de **pour** sont divisées entre les threads de l'équipe.  L'exactitude d'un programme ne doit pas dépendre de quel thread effectue une itération particulière.  La valeur de *chunk\_size*, si elle est spécifiée, doit être une expression entière indifférente de boucle avec une valeur positive.  Il n'existe aucune synchronisation pendant l'évaluation de cette expression.  Par conséquent, tous les effets secondaires évalués produisent des résultats indéterminés.  *Le type* de planification peut avoir l'une des valeurs suivantes :  
  
 Valeurs *de type* de clause de **planification** du TABLE 2\-1  
  
|||  
|-|-|  
|static|Lorsque **planification \(statique,** *chunk\_size***\)** est spécifié, les itérations sont divisés en segments d'une taille spécifiée par *chunk\_size*.  Les segments sont statiquement assignés aux threads de l'équipe de façon circulaire dans l'ordre du nombre de threads.  Lorsque aucun *chunk\_size* est spécifié, l'espace d'itération est divisé en segments qui sont pas égales en taille, avec un segment assigné à chaque thread.|  
|dynamic|Lorsque **planifier \(dynamique,** *chunk\_size***\)** est spécifié, les itérations sont divisés en une série de segments, chacun contenant *chunk\_size* des itérations.  Chaque segment est assigné à un thread qui attend une assignation.  Le thread exécute le segment des itérations et attendre son assignation suivante, jusqu'à ce que segment ne correspond pas à assigner.  Notez que le dernier segment à assigner peut contenir un plus petit nombre d'itérations.  Lorsque aucun *chunk\_size* est spécifié, il a la valeur par défaut 1.|  
|guidée|Lorsque **planifier \(guidée,** *chunk\_size***\)** est spécifié, les itérations sont assignés aux threads dans les segments avec des tailles décroissant.  Lorsqu'un thread termine son segment assigné des itérations, il est dynamique assigné un autre segment, jusqu'à ce qu'aucun ne reste.  Pour *un chunk\_size* de 1, la taille de chaque segment est d'environ le nombre d'itérations non assignées divisées par le nombre de threads.  Ces tailles diminuent environ exponentiellement à 1.  Pour *un chunk\_size* avec la valeur *k* supérieure à 1, les tailles diminuent environ exponentiellement *à k*, mais que le dernier segment peut avoir moins de les itérations *de k* .  Lorsque aucun *chunk\_size* est spécifié, il a la valeur par défaut 1.|  
|runtime|Lorsque **planifier \(runtime\)** est spécifié, la décision concernant la planification est différée jusqu ' à le moment de l'exécution.  *Le type* de planification et la taille de segments peuvent être choisis au moment de l'exécution en définissant la variable d'environnement **OMP\_SCHEDULE**.  Si cette variable d'environnement n'est pas définie, la planification résultant implémentation\-est défini.  Lorsque **planifier \(runtime\)** est spécifié, *chunk\_size* ne doit pas nécessairement être spécifié.|  
  
 En l ' absence d'une clause définie explicitement de **planification** , **planification** par défaut implémentation\-est défini.  
  
 Un programme OpenMP\-conforme ne doit pas dépendre d'un calendrier particulier pour l'exécution correcte.  Un programme ne doit pas dépendre d' *un type* de planification se conformant précisément à la description données ci\-dessus, car il est possible d'avoir des modifications dans les implémentations du même *type* de planification entre différents compilateurs.  Les descriptions peuvent être utilisées pour sélectionner la planification qui est adapté à une situation particulière.  
  
 la clause de **dimensionné** doit être présente où les directives de **dimensionné** les lient à l'élément de **pour** .  
  
 Il existe un cloisonnement implicite à la fin d'un élément de **pour** à moins qu'une clause de **nowait** soit spécifiée.  
  
 Les restrictions à la directive de **pour** sont les suivantes :  
  
-   la boucle de **pour** doit être un bloc structuré, et, en outre, son exécution ne doit pas être terminée par une instruction de **saut** .  
  
-   Les valeurs des expressions de contrôle de boucle de la boucle de **pour** associée à une directive de **pour** doivent être identiques de tous les threads dans l'équipe.  
  
-   la variable d'itération de boucle de **pour** doit avoir un type d'entier signé.  
  
-   Uniquement une clause unique de **planification** peut apparaître sur une directive de **pour** .  
  
-   Uniquement une clause unique de **dimensionné** peut apparaître sur une directive de **pour** .  
  
-   Uniquement une clause unique de **nowait** peut apparaître sur une directive de **pour** .  
  
-   Il n'est pas spécifié si ou la fréquence des effets secondaires dans les expressions *de chunk\_size*, *\#*, *de b*, ou *augmenter* se produisent.  
  
-   La valeur de l'expression *de chunk\_size* doit être la même pour tous les threads de l'équipe.  
  
## Références croisées :  
  
-   **privé**, **firstprivate**, **elle**, et les clauses de **réduction** , consultez [section 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) à la page 25.  
  
-   La variable d'environnement**OMP\_SCHEDULE** , consultez [section 4,1](../../parallel/openmp/4-1-omp-schedule.md) à la page 48.  
  
-   l'élément de**dimensionné** , consultez [section 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) à la page 22.  
  
-   [annexe D](../../parallel/openmp/d-using-the-schedule-clause.md), la page 93, fournit plus d'informations sur l'utilisation de la clause de planification.