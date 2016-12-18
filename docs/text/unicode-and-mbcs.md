---
title: "Unicode et MBCS | Microsoft Docs"
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
  - "MBCS [C++], Unicode"
  - "MFC [C++], jeux de caractères"
  - "jeux de caractères [C++], multioctets"
  - "bibliothèques runtime [C++], portabilité de langage"
  - "jeux de caractères [C++], Unicode"
  - "Unicode [C++], fonctions MFC et runtime C"
  - "caractères multioctets (C++)"
  - "runtime [C++], portabilité de langage"
ms.assetid: 677baec6-71b4-4579-94df-64f18bc117c4
caps.latest.revision: 9
caps.handback.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Unicode et MBCS
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La bibliothèque MFC \(Microsoft Foundation Classes\), la bibliothèque Runtime C pour Visual C\+\+ et l'environnement de développement Visual C\+\+ aident à la programmation internationale.  Elles fournissent :  
  
-   Une prise en charge pour la norme Unicode sous Windows 2000 \(anciennement Windows NT\).  Unicode est la norme actuelle et doit être utilisé dès que possible.  
  
     Unicode est un encodage de caractères sur 16 bits, permettant l'encodage pour toutes les langues.  Tous les caractères ASCII sont inclus dans Unicode en tant que caractères élargis.  
  
    > [!NOTE]
    >  La norme Unicode n'est pas prise en charge sous Windows 95, Windows 98 ou Windows Millennium.  
  
-   Une prise en charge pour un formulaire MBCS \(MultiByte Character Set\) appelé jeu de caractères DBCS \(Double Byte Character Set\) sur toutes les plateformes.  
  
     Les caractères DBCS sont composés d'un ou deux octets.  Certaines plages d'octets sont mises de côté pour une utilisation en tant que « octets de tête ».  Un octet de tête indique qu'il comprend avec l'« octet de queue » un caractère unique de deux octets.  Vous devez effectuer le suivi des octets de tête.  Dans un jeu de caractères multioctets, les octets de tête font partie d'une plage spécifique, ainsi que les octets de queue.  Lorsque ces plages se superposent, il peut être nécessaire d'évaluer le contexte pour déterminer si un octet donné fonctionne en tant qu'octet de tête ou octet de queue.  
  
-   Une prise en charge des outils qui simplifie la programmation MBCS des applications écrites pour les marchés internationaux.  
  
     Lorsqu'il est exécuté sur une version MBCS du système d'exploitation Windows 2000, l'environnement de développement Visual C\+\+, y compris l'éditeur de code source intégré, le débogueur et les outils de ligne de commande, est compatible MBCS.  Pour plus d'informations, consultez [Prise en charge MBCS dans Visual C\+\+](../text/mbcs-support-in-visual-cpp.md).  
  
> [!NOTE]
>  Dans cette documentation, MBCS est utilisé pour décrire la prise en charge non\-Unicode pour les caractères élargis.  Dans Visual C\+\+, MBCS signifie toujours DBCS.  Les jeux de caractères de plus de deux octets ne sont pas pris en charge.  
  
 Par définition, le jeu de caractères ASCII est un sous\-ensemble de tous les jeux de caractères multioctets.  Dans de nombreux jeux de caractères multioctets, chaque caractère de la plage 0x00 – 0x7F est identique au caractère qui a la même valeur dans le jeu de caractères ASCII.  Par exemple, dans les chaînes de caractères ASCII et MBCS, le caractère **NULL** d'un octet \('\\0'\) a la valeur 0x00 et indique le caractère de fin null.  
  
## Voir aussi  
 [Texte et chaînes](../text/text-and-strings-in-visual-cpp.md)   
 [Compatibilité internationale](../text/international-enabling.md)