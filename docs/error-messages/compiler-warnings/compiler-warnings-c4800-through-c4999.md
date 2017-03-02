---
title: "C4800 d’avertissements du compilateur à C4999 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4806
- C4807
- C4810
- C4811
- C4812
- C4813
- C4816
- C4817
- C4822
- C4825
- C4827
- C4872
- C4880
- C4881
- C4882
- C4900
- C4910
- C4912
- C4913
- C4916
- C4918
- C4920
- C4921
- C4925
- C4926
- C4932
- C4934
- C4935
- C4936
- C4937
- C4938
- C4939
- C4944
- C4947
- C4950
- C4951
- C4952
- C4953
- C4954
- C4955
- C4956
- C4957
- C4958
- C4959
- C4960
- C4961
- C4962
- C4963
- C4966
- C4970
- C4971
- C4972
- C4973
- C4974
- C4981
- C4985
- C4987
- C4988
- C4989
- C4990
- C4991
- C4992
- C4997
- C4998
- C4999
- C4808
- C4809
dev_langs:
- C++
ms.assetid: c3182430-8b3b-4ab2-a532-5cd436707dc8
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: a30a9d6a60890d0fbb4abf78df8fda4631340a6d
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warnings-c4800-through-c4999"></a>C4800 d’avertissements du compilateur à C4999
Les articles de cette partie de la documentation contiennent des informations sur un sous-ensemble des avertissements du compilateur Visual C++. Vous pouvez accéder à ces informations ici ou dans la fenêtre Sortie dans Visual Studio, vous pouvez sélectionner un numéro d’erreur et appuyez sur la touche F1.  
  
## <a name="in-this-section"></a>Dans cette section  
  
|Avertissement|Message|  
|-------------|-------------|  
|[Avertissement (niveau 3) du compilateur C4800](../../error-messages/compiler-warnings/compiler-warning-level-3-c4800.md)|'type' : valeur forcée à booléenne 'true' ou 'false' (avertissement sur les performances)|  
|[Compilateur avertissement (niveau 1) C4803](../../error-messages/compiler-warnings/compiler-warning-level-1-c4803.md)|'méthode' : la méthode raise a une classe de stockage différente de celle de l’événement, 'événement'|  
|[Compilateur avertissement (niveau 1) C4804](../../error-messages/compiler-warnings/compiler-warning-level-1-c4804.md)|'opération' : utilisation risquée du type 'bool' dans l’opération|  
|[Compilateur avertissement (niveau 1) C4805](../../error-messages/compiler-warnings/compiler-warning-level-1-c4805.md)|'opération' : mélange risqué de type 'type' et de type 'type' dans l’opération|  
|Avertissement du compilateur (niveau 1) C4806|'opération' : opération risquée : aucune valeur de type 'type' promue en type 'type' ne peut être la constante donnée|  
|Avertissement du compilateur (niveau 1) C4807|'opération' : mélange risqué de type 'type' et de champ de bits signé de type 'type'|  
|Avertissement du compilateur (niveau 1) C4808|'valeur' case n’est pas une valeur valide pour la condition switch de type 'bool'|  
|Avertissement du compilateur (niveau 1) C4809|l'instruction switch a une étiquette 'default' redondante ; toutes les étiquettes 'case' possibles sont fournies|  
|Avertissement du compilateur (niveau 1) C4810|valeur de pragma pack(show) == n|  
|Avertissement du compilateur (niveau 1) C4811|valeur de pragma conform(forScope, show) == value|  
|Avertissement du compilateur (niveau 1) C4812|style de déclaration obsolète : utilisez 'nouvelle_syntaxe' à la place|  
|Avertissement du compilateur (niveau 1) C4813|'fonction' : une fonction friend d’une classe locale doit avoir été précédemment déclarée|  
|Avertissement du compilateur (niveau 4) C4816|'param' : paramètre a un tableau de taille zéro qui sera tronqué (sauf si l’objet est passé par référence)|  
|Avertissement du compilateur (niveau 1) C4817|'membre' : utilisation non conforme de '.' pour accéder à ce membre ; compilateur remplacé par '->'|  
|[Erreur C4819 de compilateur avertissement (niveau 1)](../../error-messages/compiler-warnings/compiler-warning-level-1-c4819.md)|Le fichier contient un caractère qui ne peut pas être représenté dans la page de codes actuelle (numéro). Enregistrez le fichier au format Unicode pour éviter la perte de données|  
|[Compilateur avertissement (niveau 4) C4820](../../error-messages/compiler-warnings/compiler-warning-level-4-c4820.md)|'octets' octets de remplissage ajoutés après construction 'nom_membre'|  
|[Compilateur avertissement (niveau 1) C4821](../../error-messages/compiler-warnings/compiler-warning-level-1-c4821.md)|Impossible de déterminer le type d'encodage Unicode, enregistrez le fichier avec la signature (BOM)|  
|Avertissement du compilateur (niveau 1) C4822|'fonction membre' : fonction membre de classe locale n’a pas de corps|  
|[Compilateur avertissement (niveau 3) C4823](../../error-messages/compiler-warnings/compiler-warning-level-3-c4823.md)|'fonction' : utilise des pointeurs épingle mais déroulement sémantique n’est pas activée. Utilisez /EHa|  
|Avertissement du compilateur (niveau 4) C4825||  
|Avertissement du compilateur (niveau 3) C4827|Une méthode 'ToString' publique avec 0 paramètre doit être marquée comme virtual et override|  
|[Compilateur avertissement (niveau 1) C4829](../../error-messages/compiler-warnings/compiler-warning-level-1-c4829.md)|Paramètres potentiellement incorrects de la fonction main. Pensez « int principale (Platform::Array\<Platform::String ^ > ^ argv)'|  
|[Compilateur avertissement (niveau 1) C4835](../../error-messages/compiler-warnings/compiler-warning-level-1-c4835.md)|'variable' : l’initialiseur des données exportées ne sera pas exécuté jusqu'à ce que le code managé pour la première fois dans l’assembly hôte|  
|[Compilateur avertissement (niveau 1) C4838](../../error-messages/compiler-warnings/compiler-warning-level-1-c4838.md)|conversion de 'type_1' en 'type_2' requiert une conversion restrictive|  
|[Avertissement du compilateur C4867](../../error-messages/compiler-warnings/compiler-warning-c4867.md)|'fonction' : appel de fonction pas de liste d’arguments ; Utilisez 'appel' pour créer un pointeur vers membre|  
|[C4868 d’avertissement du compilateur](../../error-messages/compiler-warnings/compiler-warning-c4868.md)|compilateur de 'file(line_number)' ne peut pas appliquer ordre d’évaluation de gauche à droite dans la liste d’initialisation entre accolades|  
|Avertissement du compilateur (niveau 2) C4872|division par zéro en virgule flottante détectée lors de la compilation du graphique des appels pour concurrency::parallel_for_each à l'emplacement '%s'|  
|Avertissement du compilateur (niveau 1) C4880|conversion de 'type_1 const' en 'type_2' : conversion suite constness à partir d’un pointeur ou une référence peut entraîner un comportement non défini dans une fonction amp restreint|  
|Avertissement du compilateur (niveau 4) C4881|le constructeur ou le destructeur ne sera pas appelé pour la variable tile_static 'variable'|  
|Avertissement du compilateur (niveau 1) C4882|le passage de foncteurs avec opérateurs d'appels non const à concurrency::parallel_for_each est déconseillé|  
|Avertissement C4900 du compilateur|Incompatibilité il de 'outil1' version 'version1' et 'outil2' version 'version2'|  
|[Compilateur avertissement (niveau 1) C4905](../../error-messages/compiler-warnings/compiler-warning-level-1-c4905.md)|cast de littéral de chaîne étendu en 'LPSTR'|  
|[Compilateur avertissement (niveau 1) C4906](../../error-messages/compiler-warnings/compiler-warning-level-1-c4906.md)|cast de littéral de chaîne en 'LPWSTR'|  
|Avertissement du compilateur (niveau 1) C4910|«\<identificateur > : '__declspec (dllexport)' et 'extern' sont incompatibles sur une instanciation explicite|  
|Avertissement du compilateur (niveau 1) C4912|'attribute' : comportement indéfini de l’attribut sur un UDT imbriqué|  
|Avertissement du compilateur (niveau 4) C4913|l'opérateur binaire défini par l'utilisateur ',' existe mais aucune surcharge n'a pu convertir tous les opérandes, opérateur binaire intégré par défaut ',' utilisé|  
|Avertissement du compilateur (niveau 1) C4916|pour avoir un dispid, '%$S' : doit être présenté(e) par une interface|  
|[Compilateur avertissement (niveau 1) C4917](../../error-messages/compiler-warnings/compiler-warning-level-1-c4917.md)|'déclarateur' : un GUID ne peut être associé à une classe, interface ou une espace de noms|  
|Avertissement du compilateur (niveau 4) C4918|'caractère' : caractère non valide dans la liste d’optimisation pragma|  
|Avertissement du compilateur (niveau 1) Avertissement C4920 :|enum enum membre member_1 = value_1 déjà rencontré dans enum enum comme member_2 = value_2|  
|Avertissement du compilateur (niveau 3) C4921|'%s' : la valeur d'attribut '%s' ne doit pas être spécifiée plusieurs fois|  
|Avertissement du compilateur (niveau 1) C4925|'méthode' : la méthode dispinterface ne peut pas être appelée à partir d’un script|  
|Avertissement du compilateur (niveau 1) C4926|'identifier' : symbole déjà défini : attributs ignorés|  
|[Compilateur avertissement (niveau 1) C4927](../../error-messages/compiler-warnings/compiler-warning-level-1-c4927.md)|conversion non conforme ; plusieurs conversions définies par l'utilisateur ont été appliquées implicitement|  
|[Compilateur avertissement (niveau 1) C4928](../../error-messages/compiler-warnings/compiler-warning-level-1-c4928.md)|initialisation de copie non conforme ; plusieurs conversions définies par l'utilisateur ont été appliquées implicitement|  
|[Compilateur avertissement (niveau 1) C4929](../../error-messages/compiler-warnings/compiler-warning-level-1-c4929.md)|'fichier' : typelibrary contient une union ; en ignorant le qualificateur « embedded_idl »|  
|[Compilateur avertissement (niveau 1) C4930](../../error-messages/compiler-warnings/compiler-warning-level-1-c4930.md)|'prototype' : fonction prototypée non appelée (était une définition de variable souhaitée ?)|  
|[Compilateur avertissement (niveau 4) C4931](../../error-messages/compiler-warnings/compiler-warning-level-4-c4931.md)|bibliothèque de types présumée construite pour des pointeurs 'nombre' bits|  
|Avertissement du compilateur (niveau 4) C4932|__identifier (identificateur) et \__identifier(identifier) sont impossibles à distinguer|  
|Avertissement du compilateur (niveau 1) C4934|'__delegate (Multicast)' est désapprouvé, utilisez '\__delegate' à la place|  
|Avertissement du compilateur (niveau 1) C4935|Spécificateur d’accès à l’assembly modifié à partir de 'accès'|  
|Avertissement du compilateur (niveau 1) C4936|ce __declspec est pris en charge uniquement lorsqu'il est compilé avec /clr ou /clr:pure|  
|Avertissement du compilateur (niveau 4) C4937|impossible de distinguer 'text1' et 'text2' comme arguments de 'directive'|  
|Avertissement du compilateur (niveau 4) C4938|'var' : variable de réduction de virgule flottante peut provoquer des résultats incohérents sous/fp : strict ou #pragma fenv_access|  
|Avertissement C4939 du compilateur|#pragma vtordisp est déconseillée et sera supprimée dans une prochaine version de Visual C++|  
|Avertissement du compilateur (niveau 1) C4944|'symbole' : Impossible d’importer le symbole de 'assembly1' : car 'symbole' existe déjà dans la portée actuelle|  
|[Compilateur avertissement (niveau 1) C4945](../../error-messages/compiler-warnings/compiler-warning-level-1-c4945.md)|'symbole' : Impossible d’importer le symbole de 'assembly1' : car 'symbole' a déjà été importé d’un autre assembly 'assembly2'|  
|[Compilateur avertissement (niveau 1) C4946](../../error-messages/compiler-warnings/compiler-warning-level-1-c4946.md)|reinterpret_cast utilisé entre des classes connexes : 'classe1' et 'classe2'|  
|Avertissement du compilateur (niveau 1) C4947|'type_ou_membre' : marqué comme obsolète|  
|[Compilateur avertissement (niveau 2) C4948](../../error-messages/compiler-warnings/compiler-warning-level-2-c4948.md)|type de retour de 'accesseur' ne correspond pas au dernier type de paramètre de l’accesseur Set correspondant|  
|[Avertissement (niveaux 1 et 4) du compilateur C4949](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4949.md)|les pragmas 'managed' et 'unmanaged' sont significatifs uniquement lorsque vous compilez avec ' / clr [ : option]'|  
|Avertissement du compilateur (niveau 1) C4950|'type_ou_membre' : marqué comme obsolète|  
|Avertissement C4951 du compilateur|'function' a été modifié depuis que les données de profil ont été regroupées ; données de profil de fonction non utilisées|  
|Avertissement C4952 du compilateur|'fonction' : aucune donnée de profil trouvée dans la base de données du programme 'fichier_pgd'|  
|Avertissement C4953 du compilateur|Inline 'fonction' a été modifié depuis le rassemblement des données de profil ne pas|  
|Avertissement C4954 du compilateur|'fonction' : non profilé (contient l’expression de switch __int64)|  
|Avertissement C4955 du compilateur|'importation2' : importation ignorée ; déjà importé à partir de 'importation1'|  
|Avertissement du compilateur (niveau 1) C4956|'type' : ce type n’est pas vérifiable|  
|Avertissement du compilateur (niveau 1) C4957|'cast' : cast explicite de 'un cast du type' en 'cast_to' n’est pas vérifiable|  
|Avertissement du compilateur (niveau 1) l’erreur C4958|'opération' : opération arithmétique de pointeur n’est pas vérifiable|  
|Avertissement du compilateur (niveau 1) C4959|Impossible de définir un type non managé 'type' / clr : safe, car l’accès à ses membres génère du code non vérifiable|  
|Avertissement C4960 du compilateur|'function' est trop grand pour être profilé|  
|Avertissement C4961 du compilateur|Aucune donnée de profil n’a été fusionnée dans 'fichier .pgd', les optimisations guidées par profil sont désactivées|  
|Avertissement C4962 du compilateur|'fonction' : les optimisations guidées par profil désactivées, car elles génèrent des incohérences au niveau des données de profil|  
|Avertissement C4963 du compilateur|%s : aucune donnée de profil ; autres options du compilateur ont été utilisées dans la génération instrumentée|  
|[Compilateur avertissement (niveau 1) C4964](../../error-messages/compiler-warnings/compiler-warning-level-1-c4964.md)|Aucune option d'optimisation n'a été spécifiée ; les informations de profil ne seront pas recueillies|  
|[Compilateur avertissement (niveau 1) C4965](../../error-messages/compiler-warnings/compiler-warning-level-1-c4965.md)|boxing implicite de l'entier 0 ; utilisez nullptr ou effectuez un cast explicite|  
|Avertissement C4966 du compilateur|'%s' a une annotation __code_seg avec un nom de segment non pris en charge, l'annotation est ignorée|  
|Avertissement C4970 du compilateur|constructeur délégué : objet cible ignoré, car '%$pS' est statique|  
|Avertissement du compilateur (niveau 1) C4971|Ordre des arguments : \<objet cible >, \<cible fonction > de constructeur délégué est désapprouvé, utilisez \<cible (fonction) >, \<objet cible = » « >|  
|Avertissement du compilateur (niveau 1) C4972|La modification ou le traitement direct du résultat d'une conversion unboxing comme lvalue est non vérifiable|  
|Avertissement C4973 du compilateur|'%$S' : marqué comme déconseillé|  
|Avertissement C4974 du compilateur|'%$S' : marqué comme déconseillé|  
|Avertissement C4981 du compilateur|Warbird : fonction '%$pD' marquée comme __forceinline non inline, car elle contient une sémantique des exceptions|  
|Avertissement du compilateur (niveau 3) C4985|nom du symbole ' : attributs absents de la déclaration précédente.|  
|[C4986 d’avertissement du compilateur](../../error-messages/compiler-warnings/compiler-warning-c4986.md)|'%$pS' : la spécification d'exception ne correspond pas à la déclaration précédente|  
|Avertissement du compilateur (niveau 4) C4987|extension non standard utilisée : 'throw (...)'|  
|Avertissement du compilateur (niveau 4) C4988|'%$S' : variable déclarée en dehors de la portée classe/fonction|  
|Avertissement C4989 du compilateur|'%s' : le type a des définitions en conflit.|  
|Avertissement C4990 du compilateur|Warbird : %s|  
|Avertissement C4991 du compilateur|Warbird : fonction '%$pD' marquée comme __forceinline non inline, car le niveau de protection de l'inlinee est supérieur à celui du parent|  
|Avertissement C4992 du compilateur|Warbird : fonction '%$pD' marquée comme __forceinline non inline, car elle contient un assembly inline qui ne peut pas être protégé|  
|[Compilateur avertissement (niveau 3) C4995](../../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)|'fonction' : nom a été marqué comme #pragma deprecated|  
|[Compilateur avertissement (niveau 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)|'%$pS': %$*|  
|Avertissement du compilateur (niveau 1) C4997|'classe' : une coclasse n’implémente pas d’interface COM ou de pseudo-interface|  
|Avertissement du compilateur (niveau 1) C4998|ÉCHEC DE L'ATTENTE : %s(%d)|  
|Avertissement C4999 du compilateur|AVERTISSEMENT INCONNU %$N Choisissez la commande Support technique du menu ? (Aide) de Visual C++ %$N ou ouvrez le fichier d'aide du Support technique pour plus d'informations|
