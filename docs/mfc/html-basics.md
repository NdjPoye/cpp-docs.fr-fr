---
title: "&#201;l&#233;ments fondamentaux relatifs &#224; HTML | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HTML, à propos de HTML"
ms.assetid: aab8ea9f-12d4-4bdd-a585-ac3124081a2a
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# &#201;l&#233;ments fondamentaux relatifs &#224; HTML
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La plupart des navigateurs ont la capacité d'examiner la source HTML les pages que vous recherchez.  Lorsque vous affichez la source vous verrez plusieurs balises HTML, entourées par des signes inférieur et supérieur \(\<\>\), entremêlés avec le texte.  
  
 Les étapes ci\-desous utilisent les balises HTML pour générer une page Web.  Dans ces étapes, vous taperez le texte en clair dans un fichier dans le Bloc\-notes, apporterez des modifications, enregistrerez le fichier, puis rechargerez la page du navigateur pour afficher vos modifications.  
  
#### Pour créer un fichier HTML  
  
1.  Ouvrez le Bloc\-notes ou un éditeur de texte brut.  
  
2.  Dans le menu **Fichier**, cliquez sur `New`.  
  
3.  Tapez les lignes suivantes :  
  
    ```  
    <HTML>  
    <HEAD>  
    <TITLE>Top HTML Tags</TITLE>  
    </HEAD>  
    </HTML>  
    ```  
  
4.  Dans le menu de **Fichier** , choisissez **Enregistrer**, et enregistrez le fichier sous c:\\webpages\\First.htm.  Laissez le fichier ouvert dans l'éditeur de code.  
  
5.  Basculez vers votre navigateur, et du menu du **Fichier** , choisissez **Ouvrir**, ou tapez `file://C:/webpages/first.htm` dans la zone d'édition de l'URL du navigateur.  Vous devez voir une page vide à la fenêtre attribuer un libelle « balises HTML principales »  
  
     Notez les indicateurs sont appariés et inclus entre crochets des signes inférieur et supérieur.  Les balises ne respectent pas la casse, mais la mise en majuscules est souvent utilisée pour distinguer les balises.  
  
     La balise \<HTML\> de débute du document, et l'indicateur \<\/HTML\> le termine.  La terminaison d'une balise \(pas toujours nécessaire\) est la même que la balise d'ouverture mais a une barre oblique \(\/\) devant la balise.  Il ne doit y avoir aucun espace entre le crochet pointu \(\<\) et le début de l'indicateur.  
  
6.  Revenez au Bloc\-notes, et après la ligne \<\/HEAD\>, tapez :  
  
    ```  
    <BODY>  
    HTML is swell.  
    Life is good.  
    </BODY>  
    ```  
  
7.  Dans le menu **Fichier**, cliquez sur **Enregistrer** .  
  
8.  Basculez vers votre navigateur et actualisez la page.  
  
     Les mots apparaissent dans la zone client de votre fenêtre de navigateur.  Notez que votre retour chariot est ignoré.  Si vous souhaitez avoir un saut de ligne, vous devez inclure ue balise `<BR>` après la première ligne.  
  
     Pour toutes les étapes qui suivent, insérez le texte n'importe où entre \<BODY\> et \<\/BODY\> pour l'ajouter au corps du document.  
  
9. Ajoutez un en\-tête :  
  
    ```  
    <H3>Here's the big picture</H3>  
    ```  
  
10. Ajouter une image, avec d'un fichier .gif enregistré dans le même répertoire que votre page :  
  
    ```  
    <IMG src="yourfile.gif">  
    ```  
  
11. Ajoutez une liste :  
  
    ```  
    <UL>Make me an unordered list.  
    <LI>One programmer</LI>  
    <LI>Ten SDKs</LI>  
    <LI>Great Internet Apps</LI>  
    </UL>  
    ```  
  
12. pour numéroter la liste, utilisez les balises \<OL\> et \<\/OL\> à la place de \<UL\> et \<\/UL\>.  
  
 Cela peut vous aider à démarrer.  Si vous consultez une fonctionnalité intéressante sur une page Web, déterminez comment elle a été créée en examinant la source HTML.  Les éditeurs HTML tels que Microsoft Front Page peuvent être utilisés pour créer les pages simples et avancées.  
  
 Voici la source HTML complète pour le fichier que vous aviez créé :  
  
```  
<HTML>  
<HEAD>  
<TITLE>Top HTML Tags</TITLE>  
</HEAD>  
<BODY>  
HTML is swell.<BR>  
Life is good.  
<H3>Here's the big picture</H3>  
<IMG src="yourfile.gif">  
<UL>Make me an unordered list.  
<LI>One programmer</LI>  
<LI>Ten SDKs</LI>  
<LI>Great Internet Apps</LI>  
</UL>  
</BODY>  
</HTML>  
```  
  
 Pour une description complète des balises, attributs, et extensions, consultez la spécification du langage HTML \(HTML\) :  
  
 [http:\/\/www.w3.org\/pub\/WWW\/MarkUp\/](http://www.w3.org/pub/WWW/MarkUp/)  
  
## Voir aussi  
 [Éléments fondamentaux relatifs à la programmation Internet MFC](../mfc/mfc-internet-programming-basics.md)