---
title: Erreur RW2002 du compilateur de ressources | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RW2002
dev_langs:
- C++
helpviewer_keywords:
- RW2002
ms.assetid: b1d1a49b-b50b-4b0b-9f09-c7762e2dbe8f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb42298a7140439e3578281de60075f540b09175
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="resource-compiler-error-rw2002"></a>Erreur RW2002 du compilateur de ressources 
Erreur d’analyse  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Pour corriger en vérifiant les causes possibles suivantes  
  
1.  **Type d’accélérateur requis (ASCII ou VIRTKEY)**  
  
     Le champ `type` de l’instruction **ACCELERATORS** doit contenir la valeur ASCII ou VIRTKEY.  
  
2.  **BEGIN attendu dans la table d’accélérateurs**  
  
     Le mot clé **BEGIN** doit suivre immédiatement le mot clé **ACCELERATORS** .  
  
3.  **BEGIN attendu dans la boîte de dialogue**  
  
     Le **commencer** mot clé doit suivre immédiatement le **boîte de dialogue** (mot clé).  
  
4.  **BEGIN attendu dans le menu**  
  
     Le mot clé **BEGIN** doit suivre immédiatement le mot clé **MENU** .  
  
5.  **BEGIN attendu dans RCData**  
  
     Le mot clé **BEGIN** doit suivre immédiatement le mot clé **RCDATA** .  
  
6.  **Mot clé BEGIN attendu dans la table de chaînes**  
  
     Le **commencer** mot clé doit suivre immédiatement le **STRINGTABLE** (mot clé).  
  
7.  **Impossible de réutiliser les constantes de chaîne**  
  
     À l’aide de la même valeur à deux reprises dans un **STRINGTABLE** instruction. Assurez-vous que vous n’utilisez pas plusieurs chevauchement des valeurs décimales et hexadécimales. Chaque ID d’une **STRINGTABLE** doit être unique. Pour une efficacité maximale, utilisez des constantes contiguës commençant par un multiple de 16.  
  
8.  **Caractère de contrôle hors plage [^ A - ^ Z]**  
  
     Un caractère de contrôle dans l’instruction **ACCELERATORS** n’est pas valide. Le caractère qui suit le signe insertion (**^**) doit être compris entre A et Z, inclusif.  
  
9. **menus vides non autorisés**  
  
     Un **fin** mot clé apparaît avant les éléments de menu sont définis dans le **MENU** instruction. Le compilateur de ressources n’autorise pas les menus vides. Assurez-vous que vous n’avez pas de guillemets ouvrants le **MENU** instruction.  
  
10. **END attendu dans la boîte de dialogue**  
  
     Le **fin** mot clé doit se produire à la fin d’un **boîte de dialogue** instruction. Assurez-vous qu’il n’y aucun guillemet ouvrant à partir de l’instruction précédente.  
  
11. **END attendu dans le menu**  
  
     Le mot clé **END** doit figurer à la fin d’une instruction **MENU** . Assurez-vous que vous n’avez pas des guillemets ouverts ou une paire d’instructions **BEGIN** et **END** sans correspondance.  
  
12. **Virgule attendue dans la Table d’accélérateurs**  
  
     Le compilateur de ressources exige une virgule entre les champs `event` et *idvalue* dans l’instruction **ACCELERATORS** .  
  
13. **nom de classe de contrôle attendu**  
  
     Le `class` champ un **contrôle** instruction dans le **boîte de dialogue** instruction doit être un des types suivants : bouton, COMBOBOX, EDIT, LISTBOX, barre de défilement, statique, ou défini par l’utilisateur. Assurez-vous que la classe est correctement orthographiée.  
  
14. **Nom de police d’attendu**  
  
     Le champ *typeface* de l’option FONT dans l’instruction **DIALOG** doit être une chaîne de caractères ASCII placée entre guillemets doubles. Ce champ spécifie le nom d’une police.  
  
15. **Valeur d’ID attendue pour menuitem**  
  
     L’instruction **MENU** doit contenir un champ *menuID* qui spécifie le nom ou le numéro qui identifie la ressource de menu.  
  
16. **Chaîne de menu attendue**  
  
     Chaque instruction **MENUITEM** et **POPUP** doit contenir un champ de *texte* . Ce champ correspond à une chaîne placée entre guillemets doubles qui spécifie le nom de l’élément de menu ou le menu contextuel. A **MENUITEM SEPARATOR** instruction ne requiert pas de chaîne entre guillemets.  
  
17. **Valeur de la commande numérique attendue**  
  
     Le compilateur de ressources attendait un type numérique *idvalue* champ dans le **accélérateurs** instruction. Assurez-vous que vous avez utilisé un `#define` constante pour spécifier la valeur et que le nom est correctement orthographié.  
  
18. **Constante numérique attendue dans la table de chaînes**  
  
     Une constante numérique, définie dans une instruction `#define` , doit suivre immédiatement le mot clé **BEGIN** dans une instruction **STRINGTABLE** .  
  
19. **Taille de point numérique attendue**  
  
     Le champ *pointsize* de l’option FONT dans l’instruction **DIALOG** doit être une valeur de taille de point entière.  
  
20. **constante de la boîte de dialogue numérique attendue**  
  
     A **boîte de dialogue** instruction requiert des valeurs entières pour les *x, y, largeur*, et *hauteur* champs. Assurez-vous que ces valeurs sont placées après le **boîte de dialogue** (mot clé) et qu’ils ne sont pas négatifs.  
  
21. **Chaîne attendue dans STRINGTABLE**  
  
     Une chaîne est attendue après chaque valeur *stringid* d’une instruction **STRINGTABLE** .  
  
22. **Commande d’accélérateur de constante ou de chaîne attendue**  
  
     Le compilateur de ressources n’a pas pu déterminer quel type de clé est défini pour l’accélérateur. Le champ `event` de l’instruction **ACCELERATORS** peut ne pas être valide.  
  
23. **numéro d’ID est attendu**  
  
     Un numéro est attendu la `id` champ d’une instruction de contrôle de la **boîte de dialogue** instruction. Assurez-vous que vous disposez d’un nombre ou `#define` instruction pour l’ID de contrôle.  
  
24. **Chaîne entre guillemets attendue dans la classe de boîte de dialogue**  
  
     Le champ `class` de l’option CLASS figurant dans l’instruction **DIALOG** doit être un entier ou une chaîne, entre guillemets doubles.  
  
25. **Chaîne entre guillemets attendue dans le titre de la boîte de dialogue**  
  
     Le champ `captiontext` de l’option CAPTION figurant dans l’instruction **DIALOG** doit être une chaîne de caractères ASCII placée entre guillemets doubles.  
  
26. **Fichier introuvable : nom de fichier**  
  
     Le fichier spécifié sur la ligne de commande du compilateur de ressources est introuvable. Vérifiez que le fichier a été déplacé vers un autre répertoire et que le nom de fichier ou le chemin est correct. Les fichiers sont recherchés à l’aide du **INCLUDE** variable d’environnement ou le paramètre de Visual Workbench, s’il est disponible.  
  
27. **Les noms de police doivent être des ordinaux**  
  
     Le *pointsize* champ dans l’instruction de la police doit être un entier, pas une chaîne.  
  
28. **Accélérateur non valide**  
  
     Un champ `event` de l’instruction **ACCELERATORS** n'a pas été reconnu ou sa longueur dépasse deux caractères.  
  
29. **Type d’accélérateur non valide (ASCII ou VIRTKEY)**  
  
     Le champ `type` de l’instruction **ACCELERATORS** doit contenir la valeur ASCII ou VIRTKEY.  
  
30. **caractère de contrôle non valide**  
  
     Un caractère de contrôle dans l’instruction **ACCELERATORS** n’est pas valide. Un caractère de contrôle valide se compose d’une seule lettre (uniquement) après le signe insertion (^).  
  
31. **type de contrôle non valide**  
  
     Chaque instruction de contrôle dans un **boîte de dialogue** instruction doit être une des valeurs suivantes : case à cocher, COMBOBOX, contrôle, CTEXT, DEFPUSHBUTTON, EDITTEXT, GROUPBOX, icône, LISTBOX, LTEXT, PUSHBUTTON, RADIOBUTTON, RTEXT, barre de défilement. Assurez-vous que ces instructions de contrôle sont correctement orthographiées.  
  
32. **Type non valide**  
  
     Le type de ressource n’a pas parmi les types définis dans le fichier WINDOWS.h.  
  
33. **Chaîne de texte ou ordinal attendu dans le contrôle**  
  
     Le *texte* champ un **contrôle** instruction dans le **boîte de dialogue** instruction doit être une chaîne de texte ou un ordinal référençant le type de contrôle. S’il s’agit d’un ordinal, veillez à utiliser une instruction `#define` pour le contrôle.  
  
34. **Parenthèses non appariées**  
  
     Vérifiez que vous avez fermé chaque parenthèse ouvrante la **boîte de dialogue** instruction.  
  
35. **Valeur inattendue dans RCData**  
  
     Les valeurs de *données brutes* de l’instruction **RCDATA** doivent être des entiers ou des chaînes, séparés par une virgule. Assurez-vous de ne pas avoir oublié une virgule ou un guillemet autour d’une chaîne.  
  
36. **sous-type de menu inconnu**  
  
     Le *définition d’élément* champ le **MENU** instruction peut uniquement contenir **MENUITEM** et **POPUP** instructions.