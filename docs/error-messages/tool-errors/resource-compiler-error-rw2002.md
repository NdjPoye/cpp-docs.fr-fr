---
title: "Erreur RW2002 du compilateur de ressources  | Microsoft Docs"
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
  - "RW2002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RW2002"
ms.assetid: b1d1a49b-b50b-4b0b-9f09-c7762e2dbe8f
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur RW2002 du compilateur de ressources 
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erreur d'analyse  
  
### Pour résoudre le problème en vérifiant les causes possibles suivantes  
  
1.  **Type d'accélérateur requis \(ASCII ou VIRTKEY\)**  
  
     Le champ `type` de l'instruction **ACCELERATORS** doit contenir la valeur ASCII ou VIRTKEY.  
  
2.  **BEGIN requis dans la table d'accélérateurs**  
  
     Le mot clé **BEGIN** doit suivre immédiatement le mot clé **ACCELERATORS**.  
  
3.  **BEGIN attendu dans la boîte de dialogue**  
  
     Le mot clé **BEGIN** doit suivre immédiatement le mot clé **DIALOG**.  
  
4.  **BEGIN attendu dans le menu**  
  
     Le mot clé **BEGIN** doit suivre immédiatement le mot clé **MENU**.  
  
5.  **BEGIN attendu dans RCData**  
  
     Le mot clé **BEGIN** doit suivre immédiatement le mot clé **RCDATA**.  
  
6.  **Le mot clé BEGIN attendu dans la table de chaînes**  
  
     Le mot clé **BEGIN** doit suivre immédiatement le mot clé **STRINGTABLE**.  
  
7.  **Impossible de réutiliser les constantes de chaînes**  
  
     Vous avez utilisé deux fois la même valeur dans une instruction **STRINGTABLE**.  Évitez d'utiliser des valeurs décimales et hexadécimales qui se chevauchent.  Chaque ID d'une instruction **STRINGTABLE** doit être unique.  Pour un résultat optimal, utilisez des constantes contiguës commençant par un multiple de 16.  
  
8.  **Caractère de contrôle hors limites \[^A \- ^Z\]**  
  
     Un caractère de contrôle de l'instruction **ACCELERATORS** est non valide.  Le caractère après le signe insertion \(**^**\) doit être compris entre A et Z, inclus.  
  
9. **Menus vides non autorisés**  
  
     Un mot clé **END** apparaît alors qu'aucun élément de menu n'a été défini dans l'instruction **MENU**.  Le compilateur de ressources n'autorise pas les menus vides.  Assurez\-vous que l'instruction **MENU** ne contient pas de guillemets ouvrants.  
  
10. **END attendu dans la boîte de dialogue**  
  
     Le mot clé **END** doit apparaître à la fin d'une instruction **DIALOG**.  Assurez\-vous qu'il ne reste aucun guillemet ouvrant de l'instruction précédente.  
  
11. **END attendu dans le menu**  
  
     Le mot clé **END** doit apparaître à la fin d'une instruction **MENU**.  Assurez\-vous que l'instruction ne contient aucun guillemet ouvrant, ni d'instructions **BEGIN** et **END** dépariées.  
  
12. **Virgule attendue dans la table d'accélérateurs**  
  
     Le compilateur de ressources requiert l'insertion d'une virgule entre les champs `event` et *idvalue* de l'instruction **ACCELERATORS**.  
  
13. **Nom de classe de contrôle attendu**  
  
     Le champ `class` d'une instruction **CONTROL** de l'instruction **DIALOG** doit être de type BUTTON, COMBOBOX, EDIT, LISTBOX, SCROLLBAR, STATIC ou d'un type défini par l'utilisateur.  Assurez\-vous que le nom de la classe est correctement orthographié.  
  
14. **Nom de type de police attendu**  
  
     Le champ *typeface* de l'option FONT de l'instruction **DIALOG** doit être une chaîne de caractères ASCII placée entre guillemets.  Ce champ spécifie le nom d'une police.  
  
15. **Valeur d'ID attendue pour menuitem**  
  
     L'instruction **MENU** doit contenir un champ *menuID* indiquant le nom ou le numéro qui identifie la ressource de menu.  
  
16. **Chaîne de menu attendue**  
  
     Chaque instruction **MENUITEM** et **POPUP** doit comporter un champ *text* contenant une chaîne placée entre guillemets. Cette chaîne identifie le nom de l'élément de menu ou celui du menu contextuel.  Une instruction **MENUITEM SEPARATOR** ne requiert pas de chaîne entre guillemets.  
  
17. **Valeur de la commande numérique attendue**  
  
     Le compilateur de ressources attendait un champ *idvalue* numérique dans l'instruction **ACCELERATORS**.  Assurez\-vous que vous avez défini sa valeur à l'aide d'une constante `#define` et que son nom est correctement orthographié.  
  
18. **Constante numérique attendue dans la table de chaînes**  
  
     Une constante numérique, définie dans une instruction `#define`, doit suivre immédiatement le mot clé **BEGIN** dans une instruction **STRINGTABLE**.  
  
19. **Taille en points numérique attendue**  
  
     Le champ *pointsize* de l'option FONT dans l'instruction **DIALOG** doit être une valeur de taille en points de type Entier.  
  
20. **Constante de boîte de dialogue numérique attendue**  
  
     Une instruction **DIALOG** requiert des valeurs de type Entier pour les champs *x, y, width* et *height*.  Vérifiez que ces valeurs sont placées après le mot clé **DIALOG** et qu'elles ne sont pas négatives.  
  
21. **Chaîne attendue dans STRINGTABLE**  
  
     Une chaîne est attendue après chaque valeur *stringid* d'une instruction **STRINGTABLE**.  
  
22. **Commande d'accélérateur de constante ou de chaîne attendue**  
  
     Le compilateur de ressources n'a pas pu déterminer le type de touche définie pour l'accélérateur.  Le champ `event` de l'instruction **ACCELERATORS** est peut\-être incorrect.  
  
23. **Numéro pour l'ID attendu**  
  
     Un numéro est attendu dans le champ `id` d'une instruction de contrôle de l'instruction **DIALOG**.  Vérifiez que l'ID de contrôle est un numéro ou une instruction `#define`.  
  
24. **Chaîne entre guillemets attendue dans la classe de boîte de dialogue**  
  
     Le champ `class` de l'option CLASS d'une instruction **DIALOG** doit être un entier ou une chaîne placée entre guillemets.  
  
25. **Chaîne entre guillemets attendue dans le titre de boîte de dialogue**  
  
     Le champ `captiontext` de l'option CAPTION dans l'instruction **DIALOG** doit être une chaîne de caractères ASCII placée entre guillemets.  
  
26. **Fichier introuvable : nom de fichier**  
  
     Le fichier spécifié dans la ligne de commande du compilateur de ressources est introuvable.  Vérifiez si le fichier a été déplacé dans un autre répertoire et assurez\-vous que le nom et le chemin d'accès du fichier sont corrects.  Le compilateur recherche la variable d'environnement **INCLUDE**, ou le paramètre de Visual Workbench, s'il est disponible, dans les fichiers.  
  
27. **Les noms de polices doivent être des nombres**  
  
     Le champ *pointsize* de l'instruction FONT doit être un entier et non une chaîne.  
  
28. **Accélérateur non valide**  
  
     Un champ `event` de l'instruction **ACCELERATORS** n'a pas été reconnu ou sa longueur dépasse deux caractères.  
  
29. **Type d'accélérateur non valide \(ASCII ou VIRTKEY\)**  
  
     Le champ `type` de l'instruction **ACCELERATORS** doit contenir la valeur ASCII ou VIRTKEY.  
  
30. **Caractère de contrôle non valide**  
  
     Un caractère de contrôle de l'instruction **ACCELERATORS** est non valide.  Un caractère de contrôle valide doit uniquement comporter une lettre après le signe insertion \(^\).  
  
31. **Type de contrôle non valide**  
  
     Chaque instruction de contrôle d'une instruction **DIALOG** doit être de type CHECKBOX, COMBOBOX, CONTROL, CTEXT, DEFPUSHBUTTON, EDITTEXT, GROUPBOX, ICON, LISTBOX, LTEXT, PUSHBUTTON, RADIOBUTTON, RTEXT ou SCROLLBAR.  Vérifiez que ces instructions de contrôle sont correctement orthographiées.  
  
32. **Type non valide**  
  
     Le type de ressources n'est pas un des types définis dans le fichier WINDOWS.h.  
  
33. **Chaîne de texte ou ordinal attendu dans le contrôle**  
  
     Le champ *text* d'une instruction **CONTROL** de l'instruction **DIALOG** doit être une chaîne de texte ou un ordinal référençant le type de contrôle.  S'il s'agit d'un ordinal, veillez à utiliser une instruction `#define` pour le contrôle.  
  
34. **Parenthèses non appariées**  
  
     Vérifiez que vous avez fermé toutes les parenthèses ouvrantes figurant dans l'instruction **DIALOG**.  
  
35. **Valeur inattendue dans RCData**  
  
     Les valeurs *raw\-data* de l'instruction **RCDATA** doivent être des entiers ou des chaînes, séparés par des virgules.  Assurez\-vous que vous n'avez pas omis une virgule ou un guillemet à proximité d'une chaîne.  
  
36. **Sous\-type de menu inconnu**  
  
     Le champ *item\-definition* de l'instruction **MENU** peut uniquement contenir des instructions **MENUITEM** et **POPUP**.