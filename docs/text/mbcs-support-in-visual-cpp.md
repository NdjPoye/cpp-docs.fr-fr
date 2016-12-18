---
title: "Prise en charge MBCS dans Visual C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_mbcs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "langues asiatiques (C++)"
  - "jeux de caractères (C++), multioctets"
  - "caractères chinois (C++)"
  - "éditeur de code (C++), prise en charge MBCS"
  - "débogueur (C++), prise en charge MBCS"
  - "jeux de caractères codés sur deux octets (C++)"
  - "IME (C++)"
  - "IME (C++), MBCS"
  - "éditeur de méthode d'entrée (C++)"
  - "éditeur de méthode d'entrée (C++), MBCS"
  - "caractères japonais (C++)"
  - "caractères Kanji (prise en charge) (C++)"
  - "MBCS (C++), activer"
  - "caractères multioctets (C++)"
  - "programme NMAKE, prise en charge MBCS"
  - "éditeurs de ressources (C++), prise en charge MBCS"
  - "outils (C++), prise en charge MBCS"
ms.assetid: 6179f6b7-bc61-4a48-9267-fb7951223e38
caps.latest.revision: 7
caps.handback.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Prise en charge MBCS dans Visual C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsqu'il est exécuté sur une version MBCS du système d'exploitation Windows 2000 ou Windows XP, l'environnement de développement Visual C\+\+, y compris l'éditeur de code source intégré, le débogueur et les outils de ligne de commande, est compatible MBCS, à l'exception de la fenêtre mémoire.  
  
 La fenêtre de mémoire n'interprète pas d'octets de données caractères comme MBCS, bien qu'il puisse interpréter comme elles ANSI ou de caractères Unicode.  Les caractères ANSI sont toujours de 1 octets dans la taille et les caractères Unicode sont de 2 octets dans la taille.  Avec MBCS, les caractères peuvent être 1 ou 2 octets dans la taille et son interprétation dépend de la page de codes est utilisé.  Par conséquent, il est difficile pour la fenêtre de mémoire d'afficher de manière fiable des caractères MBCS.  La fenêtre de mémoire ne peut pas connaître quel octet est le début d'un caractère.  Le développeur peut consulter les valeurs d'octet dans la fenêtre de mémoire et chercher la valeur dans les tables pour déterminer la présentation des caractères.  Ceci est possible parce que le développeur sait l'adresse de départ d'une chaîne d'après le code source.  
  
 Visual C\+\+ accepte les caractères codés sur deux octets lorsque cela s'impose.  Cela comprend les noms de chemins d'accès et les noms de fichiers dans les boîtes de dialogue, ainsi que les entrées de texte dans l'éditeur de ressources Visual C\+\+ \(par exemple, le texte statique dans l'éditeur de boîtes de dialogue et les entrées de texte statique dans l'éditeur d'icônes\).  De plus, le préprocesseur reconnaît certaines directives codées sur deux octets, par exemple, les noms de fichiers dans les instructions `#include` et comme arguments des mots clés pragma **code\_seg** et **data\_seg**.  Dans l'éditeur de code source, les caractères codés sur deux octets dans les commentaires et les littéraux de chaîne sont acceptés, mais ne le sont pas dans les éléments du langage C\/C\+\+ \(tels que les noms de variables\).  
  
##  <a name="_core_support_for_the_input_method_editor_.28.ime.29"></a> Prise en charge pour l'éditeur de méthode d'entrée \(IME, Input Method Editor\)  
 Les applications écrites pour les marchés de l'Asie de l'est qui utilisent MBCS \(par exemple, le Japon\) prennent en charge l'IME Windows pour la saisie des caractères codés sur un et deux octets.  L'environnement de développement Visual C\+\+ contient une prise en charge pour l'IME.  Pour plus d'informations, consultez [IME, exemple : illustre la manière de contrôler le mode de l'IME et d'implémenter IME niveau 3](http://msdn.microsoft.com/fr-fr/87ebdf65-cef0-451d-a6fc-d5fb64178b14)  
  
 Les claviers japonais ne prennent pas en charge les caractères Kanji.  L'IME convertit une chaîne phonétique, entrée dans l'un des alphabets japonais \(Romaji, Katakana ou Hiragana\) dans les représentations Kanji possibles.  En cas d'ambiguïté, vous pouvez sélectionner l'une des solutions proposées.  Lorsque vous avez sélectionné le caractère Kanji, l'IME passe deux messages `WM_CHAR` à l'application de contrôle.  
  
 L'IME, activé par la combinaison de touches ALT\+\`, s'affiche sous la forme d'un jeu de boutons \(indicateur\) et d'une fenêtre de conversion.  L'application positionne la fenêtre au niveau du point d'insertion.  L'application doit gérer les messages `WM_MOVE` et `WM_SIZE` en repositionnant la fenêtre de conversion pour qu'elle corresponde au nouvel emplacement ou à la taille de la fenêtre cible.  
  
 Si vous souhaitez que les utilisateurs de votre application puissent entrer des caractères Kanji, l'application doit gérer les messages IME Windows.  Pour plus d'informations sur la programmation IME, consultez [Éditeur de méthode d'entrée](https://msdn.microsoft.com/en-us/library/ms776145.aspx).  
  
## Débogueur Visual C\+\+  
 Le débogueur Visual C\+\+ permet de définir des points d'arrêt sur les messages IME.  De plus, la fenêtre Mémoire peut afficher des caractères codés sur deux octets.  
  
## Outils de ligne de commande  
 Les outils de ligne de commande Visual C\+\+, y compris le compilateur, NMAKE et le compilateur de ressources \(RC.EXE\), sont compatibles MBCS.  Vous pouvez utiliser l'option \/c du compilateur de ressources pour modifier la page de codes par défaut lors de la compilation des ressources de votre application.  
  
 Pour changer les paramètres régionaux par défaut au moment de la compilation du code source, utilisez [\#pragma setlocale](../preprocessor/setlocale.md).  
  
## Outils graphiques  
 Les outils Windows de Visual C\+\+, tels que Spy\+\+ et les outils de modification de ressources, prennent en charge les chaînes IME.  
  
## Voir aussi  
 [Prise en charge des jeux de caractères multioctets \(MBCS\)](../text/support-for-multibyte-character-sets-mbcss.md)   
 [Conseils de programmation MBCS](../text/mbcs-programming-tips.md)