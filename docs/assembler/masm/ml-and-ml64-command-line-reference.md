---
title: "ML and ML64 Command-Line Reference | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ML"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/W* MASM compiler option"
  - "/c MASM compiler option"
  - "/EP MASM compiler option"
  - "/Fe MASM compiler option"
  - "/Zp MASM compiler option"
  - "/AT MASM compiler option"
  - "/Zm MASM compiler option"
  - "/Sf MASM compiler option"
  - "/Sp MASM compiler option"
  - "/w MASM compiler option"
  - "/Fl MASM compiler option"
  - "/coff MASM compiler option"
  - "/St MASM compiler option"
  - "/Cx MASM compiler option"
  - "/Sl MASM compiler option"
  - "/Cu MASM compiler option"
  - "MASM (Microsoft Macro Assembler), ML command-line reference"
  - "/FPi MASM compiler option"
  - "/Zf MASM compiler option"
  - "ML environment variable"
  - "/Fr MASM compiler option"
  - "/help MASM compiler option"
  - "/Sa MASM compiler option"
  - "/Zd MASM compiler option"
  - "/I MASM compiler option"
  - "/? MASM compiler option"
  - "/Bl MASM compiler option"
  - "/Fm MASM compiler option"
  - "/Fo MASM compiler option"
  - "command-line reference [ML]"
  - "/Sn MASM compiler option"
  - "/Gd MASM compiler option"
  - "/D* MASM compiler option"
  - "environment variables, ML"
  - "/Gc MASM compiler option"
  - "/F* MASM compiler option"
  - "/Sc MASM compiler option"
  - "/H MASM compiler option"
  - "/Zs MASM compiler option"
  - "/omf MASM compiler option"
  - "/Sg MASM compiler option"
  - "/Cp MASM compiler option"
  - "/Zi MASM compiler option"
  - "/nologo MASM compiler option"
  - "/Sx MASM compiler option"
  - "/WX MASM compiler option"
  - "/Ss MASM compiler option"
  - "command line, reference [ML]"
  - "/Ta MASM compiler option"
ms.assetid: 712623c6-f77e-47ea-a945-089e57c50b40
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# ML and ML64 Command-Line Reference
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compile et lie un ou plusieurs fichiers source en langage assembleur.  Les options de ligne de commande respectent la casse.  
  
 Pour plus d'informations sur ml64.exe, consultez [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## Syntaxe  
  
```  
ML [[options]] filename [[ [[options]]  filename]]  
ML64 [[options]] filename [[ [[options]]  filename]]  
...  
[[/link linkoptions]]  
```  
  
#### Paramètres  
 `options`  
 les options répertoriées dans le tableau suivant.  
  
|Option|Action|  
|------------|------------|  
|**\/AT**|active la prise en charge de minuscule\-mémoire\-modèle.  Active des messages d'erreur pour les constructions de code qui violent les spécifications des fichiers de format .com.  notez que ce n'est pas équivalent à la directive de [.MODEL](../../assembler/masm/dot-model.md)**TINY** .<br /><br /> non disponible dans ml64.exe.|  
|**\/Bl** `filename`|sélectionne un autre éditeur de liens.|  
|**\/c**|Se réunit uniquement.  Ne crée pas de liaison.|  
|**\/coff**|Génère le type commun de format \(COFF\) de fichier objet de module objet.  En général requis pour le développement de langage assembleur Win32.<br /><br /> non disponible dans ml64.exe.|  
|**\/Cp**|Casse préserve de tous les ID d'utilisateur.|  
|**\/Cu**|Mappe tous les identificateurs en majuscules \(par défaut\).<br /><br /> non disponible dans ml64.exe.|  
|**\/Cx**|La directive conserve toutes dans les symboles publics et extern.|  
|**\/D** `symbol`\[\[\=`value`\]\]|Définissez une macro de texte avec le nom spécifié.  Si `value` est manquant, il est vide.  Plusieurs jetons séparés par des espaces doivent être entre guillemets.|  
|**\/EP**|Génère une liste prétraité de source \(envoyé à STDOUT\).  Consultez **\/Sf**.|  
|**\/ERRORREPORT** \[ **NONE** &#124; **PROMPT** &#124; **QUEUE** &#124; **SEND** \]|Si ml.exe ou ml64.exe échoue au moment de l'exécution, vous pouvez utiliser **\/ERRORREPORT** pour envoyer des informations à Microsoft à propos de ces erreurs internes.<br /><br /> Pour plus d'informations sur **\/ERRORREPORT**, consultez [\/errorReport \(Signaler les erreurs internes du compilateur\)](../../build/reference/errorreport-report-internal-compiler-errors.md).|  
|**\/F** `hexnum`|Définit la taille de la pile des octets d' `hexnum` \(c'est le même qu' **\/link\/STACK**:`number`\).  la valeur doit être exprimée en notation hexadécimale.  Il doit y avoir d'espace entre **\/F** et `hexnum`.|  
|**\/Fe** `filename`|nomme le fichier exécutable.|  
|**\/Fl**\[\[`filename`\]\]|Génère une liste de code assembly.  Consultez **\/Sf**.|  
|**\/Fm**\[\[`filename`\]\]|Crée un fichier de mappage de l'éditeur de liens.|  
|**\/Fo** `filename`|Désigne un fichier objet.  Consultez la section Notes pour plus d'informations.|  
|**\/FPi**|Génère l'émulateur correctif\-UPS pour le calcul à virgule flottante \(langage mixte uniquement\).<br /><br /> non disponible dans ml64.exe.|  
|**\/Fr**\[\[`filename`\]\]|Génère un fichier du navigateur .sbr source.|  
|**\/FR**\[\[`filename`\]\]|Génère un formulaire étendu d'un fichier du navigateur .sbr source.|  
|**\/Gc**|Spécifie l'utilisation de Fortran ou d'appeler et de conventions d'affectation de noms de type Pascal de fonction.  De la même manière qu' **OPTION LANGUAGE:PASCAL**.<br /><br /> non disponible dans ml64.exe.|  
|**\/Gd**|Spécifie l'utilisation d'appeler de style C et de conventions d'affectation de noms de fonction.  De la même manière qu' **OPTION LANGUAGE:C**.<br /><br /> non disponible dans ml64.exe.|  
|**\/GZ**|Spécifie l'utilisation d'appeler et de conventions d'affectation de noms de fonctions de \_\_stdcall.  De la même manière qu' **OPTION LANGUAGE:STCALL**.<br /><br /> non disponible dans ml64.exe.|  
|**\/H** `number`|Restreint des noms externes pour compter les caractères significatifs.  La valeur par défaut est 31 caractères.<br /><br /> non disponible dans ml64.exe.|  
|**\/help**|Appels QuickHelp pour obtenir de l'aide sur ML.|  
|**\/I** `pathname`|Définit le chemin d'accès du fichier Include.  Il permet un maximum de 10 options d' **\/I** .|  
|**\/nologo**|Supprime des messages pour l'assembly a réussi.|  
|**\/omf**|Génère le type du format de fichier de module \(OMF\) objet de module objet.  **\/omf** implique **\/c**; ML.exe ne prend pas en charge la liaison des objets OMF.<br /><br /> non disponible dans ml64.exe.|  
|**\/Sa**|tourne répertorier en fonction de toutes les informations disponibles.|  
|**\/safeseh**|Marque l'objet comme ne contenir aucun gestionnaire d'exceptions ou contenir des gestionnaires d'exceptions qui sont tous déclarés avec [.SAFESEH](../../assembler/masm/dot-safeseh.md).<br /><br /> non disponible dans ml64.exe.|  
|**\/Sf**|Ajoute la liste de première exécution à répertorier le fichier.|  
|**\/Sl** `width`|Définit la largeur de ligne de la liste de source en caractères par ligne.  La plage comprise entre 60 et 255 ou 0.  La valeur par défaut est 0.  mêmes que la largeur de [PG](../../assembler/masm/page.md) .|  
|**\/Sn**|Arrête la table de symboles pour produire une liste.|  
|**\/Sp** `length`|Définit la longueur de page de la liste de source dans les lignes par page.  La plage comprise entre 10 et 255 ou 0.  La valeur par défaut est 0.  mêmes que la longueur de [PG](../../assembler/masm/page.md) .|  
|**\/Ss** `text`|Spécifie le texte pour la liste de source.  Même que le texte de [SOUS\-TITRE](../../assembler/masm/subtitle.md) .|  
|**\/St** `text`|Spécifie le titre pour la liste de source.  Même que le texte de [TITRE](../../assembler/masm/title.md) .|  
|**\/Sx**|Active les conditions false dans la liste.|  
|**\/Ta** `filename`|Compile le fichier source dont le nom ne se termine pas par l'extension .asm.|  
|**\/w**|De la même manière qu' **\/W0\/WX**.|  
|**\/W** `level`|définit le niveau d'avertissement, où `level` \= 0, 1, 2, ou 3.|  
|**\/WX**|Retourne un code d'erreur si les avertissements sont générés.|  
|**\/X**|Ignorez INCLUDE le chemin d'accès d'environnement.|  
|**\/Zd**|Génère des informations de numéro de ligne dans le fichier objet.|  
|**\/Zf**|Effectue le public de symboles.|  
|**\/Zi**|Génère des informations CodeView dans le fichier objet.|  
|**\/Zm**|Activel'option d'**M510** pour une compatibilité maximale avec MASM 5,1.<br /><br /> non disponible dans ml64.exe.|  
|**\/Zp**\[\[`alignment`\]\]|structures de paquets sur la limite d'octets spécifiée.  `alignment` peut avoir la valeur 1, 2 ou 4.|  
|**\/Zs**|Exécute une vérification de la syntaxe uniquement.|  
|**\/?**|affiche un résumé de la syntaxe de ligne de commande de ML.|  
  
 `filename`  
 Nom du fichier.  
  
 `linkoptions`  
 les options de lien.  Consultez [Options de l'Éditeur de liens](../../build/reference/linker-options.md) pour plus d'informations.  
  
## Notes  
 Certaines options de ligne de commande à ML et à ML64 sont positionnement\-sensibles.  Par exemple, car ML et ML64 peuvent accepter plusieurs options d' **\/c** , toutes les options correspondantes d' **\/Fo** doivent être spécifiées avant **\/c**.  L'exemple suivant de ligne de commande affiche une spécification de fichier objet pour chaque spécification de fichier d'assembly :  
  
 **ml.exe \/Fo a1.obj \/c a.asm \/Fo b1.obj \/c b.asm**  
  
## Variables d'environnement  
  
|Variable|Description|  
|--------------|-----------------|  
|COMPRENEZ|Spécifie le chemin de recherche des fichiers Include.|  
|ML|spécifie des options de ligne de commande par défaut.|  
|TMP|Spécifie le chemin d'accès des fichiers temporaires.|  
  
## Voir aussi  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)   
 [Microsoft Macro Assembler Reference](../../assembler/masm/microsoft-macro-assembler-reference.md)