---
title: "C4400 d’avertissements du compilateur via C4599 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4413
- C4415
- C4416
- C4417
- C4418
- C4419
- C4421
- C4423
- C4424
- C4425
- C4426
- C4427
- C4438
- C4442
- C4443
- C4444
- C4446
- C4447
- C4448
- C4449
- C4450
- C4451
- C4452
- C4453
- C4454
- C4455
- C4456
- C4457
- C4458
- C4459
- C4463
- C4464
- C4471
- C4472
- C4480
- C4482
- C4483
- C4491
- C4492
- C4493
- C4494
- C4509
- C4519
- C4531
- C4542
- C4562
- C4568
- C4569
- C4573
- C4574
- C4575
- C4582
- C4583
- C4585
- C4586
- C4587
- C4588
- C4591
- C4592
- C4593
- C4594
- C4595
dev_langs:
- C++
ms.assetid: b07850a5-ae89-48ea-bf9a-f0e30939f9b9
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 4ac033535632e94a365aa8dafd849f2ab28a3af7
ms.openlocfilehash: f6991adb0413221ddb101d07af41f83d1bbcabe2
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warnings-c4400-through-c4599"></a>C4400 d’avertissements du compilateur via C4599
Les articles de cette partie de la documentation contiennent des informations sur un sous-ensemble des avertissements du compilateur Visual C++. Vous pouvez accéder à ces informations ici ou, dans le **sortie** fenêtre dans Visual Studio, vous pouvez sélectionner un numéro d’avertissement et appuyez sur la touche F1.  
  
## <a name="in-this-section"></a>Dans cette section  
  
|Avertissement|Message|  
|-------------|-------------|  
|[Compilateur avertissement (niveau 1) C4600](../../error-messages/compiler-warnings/compiler-warning-level-1-c4600.md)|#pragma 'nom macro' : chaîne valide non vide attendue|  
|[Compilateur avertissement (niveau 4) C4400](../../error-messages/compiler-warnings/compiler-warning-level-4-c4400.md)|'type' : les qualificateurs const/volatile pour ce type ne sont pas pris en charge.|  
|[Compilateur avertissement (niveau 1) C4401](../../error-messages/compiler-warnings/compiler-warning-level-1-c4401.md)|'champ' : membre est le champ de bits|  
|[Compilateur avertissement (niveau 1) C4402](../../error-messages/compiler-warnings/compiler-warning-level-1-c4402.md)|doit utiliser l'opérateur PTR|  
|[Compilateur avertissement (niveau 1) C4403](../../error-messages/compiler-warnings/compiler-warning-level-1-c4403.md)|opérateur PTR non conforme|  
|[Compilateur avertissement (niveau 3) C4404](../../error-messages/compiler-warnings/compiler-warning-level-3-c4404.md)|point dans la directive ignoré|  
|[Compilateur avertissement (niveau 1) C4405](../../error-messages/compiler-warnings/compiler-warning-level-1-c4405.md)|'identificateur' : identificateur est un mot réservé|  
|[Compilateur avertissement (niveau 1) C4406](../../error-messages/compiler-warnings/compiler-warning-level-1-c4406.md)|opérande sur directive ignoré|  
|[Compilateur avertissement (niveau 1) C4407](../../error-messages/compiler-warnings/compiler-warning-level-1-c4407.md)|cast entre différentes représentations du pointeur en membre, le compilateur peut générer du code incorrect|  
|[Compilateur avertissement (niveau 4) C4408](../../error-messages/compiler-warnings/compiler-warning-level-4-c4408.md)|anonyme ' struct | union' n’a pas déclaré de membres de données|  
|[Compilateur avertissement (niveau 1) C4409](../../error-messages/compiler-warnings/compiler-warning-level-1-c4409.md)|taille d'instruction non conforme|  
|[Compilateur avertissement (niveau 1) C4410](../../error-messages/compiler-warnings/compiler-warning-level-1-c4410.md)|taille d'opérande non conforme|  
|[Compilateur avertissement (niveau 1) C4411](../../error-messages/compiler-warnings/compiler-warning-level-1-c4411.md)|'identificateur' : symbole se résout en registre de déplacement|  
|[Compilateur avertissement (niveau 2) C4412](../../error-messages/compiler-warnings/compiler-warning-level-2-c4412.md)|'fonction' : signature de fonction contient le type 'type' ; Objets C++ sont unsafe à passer entre le code pure et mixte ou natif.|  
|Avertissement C4413 du compilateur|'classname::member' : membre de référence est initialisé en temporaire qui ne persiste pas après l’arrêt du constructeur|  
|[Compilateur avertissement (niveau 3) C4414](../../error-messages/compiler-warnings/compiler-warning-level-3-c4414.md)|'fonction' : saut de type short vers la fonction converti en near|  
|Avertissement du compilateur (niveau 1) C4415|__declspec(code_seg('%$I')) dupliqué|  
|Avertissement du compilateur (niveau 1) C4416|__declspec(code_seg(...)) contient une chaîne vide : ignoré|  
|Avertissement du compilateur (niveau 1) C4417|une instanciation explicite du modèle ne peut pas avoir __declspec(code_seg(...)) : ignoré|  
|Avertissement du compilateur (niveau 1) C4418|__declspec(code_seg(...)) ignoré sur un enum|  
|Avertissement du compilateur (niveau 3) C4419|'%$I' n'a pas d'effet lorsqu'il est appliqué à la classe ref '%$S' privée.|  
|[Compilateur avertissement (niveau 1) C4420](../../error-messages/compiler-warnings/compiler-warning-level-1-c4420.md)|'checked_operator' : opérateur non disponible, à l’aide de 'opérateur' à la place. vérification de l’exécution peut être compromise.|  
|Avertissement du compilateur (niveau 3) C4421|'%$I' : un paramètre de référence sur une fonction pouvant être reprise est potentiellement dangereux|  
|Avertissement du compilateur (niveau 3) C4423|'std::bad_alloc' : sera intercepté par la classe ('%$T') à la ligne %d|  
|Avertissement du compilateur (niveau 3) C4424|interception de '%$T' précédée par '%$T' à la ligne %d ; il peut en résulter un comportement imprévisible si l'exception 'std::bad_alloc' est levée|  
|Avertissement du compilateur (niveau 1) C4425|Une annotation SAL ne peut pas être appliquée à '…'|  
|Avertissement C4426 du compilateur|indicateurs d’optimisation modifiés après l’inclusion de l’en-tête, peut être dû au #pragma optimize()|  
|Avertissement du compilateur (niveau 1) C4427|'%$L' : dépassement en division constante, comportement indéfini|  
|[Compilateur avertissement (niveau 4) C4429](../../error-messages/compiler-warnings/compiler-warning-level-4-c4429.md)|nom de caractère universel éventuellement incomplet ou incorrectement formé|  
|[Avertissement du compilateur C4430](../../error-messages/compiler-warnings/compiler-warning-c4430.md)|spécificateur de type manquant - int est pris en compte par défaut. Remarque : C++ ne prend pas en charge int par défaut|  
|[Compilateur avertissement (niveau 4) C4431](../../error-messages/compiler-warnings/compiler-warning-level-4-c4431.md)|spécificateur de type manquant - int est pris en compte par défaut. Remarque : C ne prend plus en charge int par défaut|  
|[Compilateur avertissement (niveau 4) C4434](../../error-messages/compiler-warnings/compiler-warning-level-4-c4434.md)|un constructeur static doit avoir un accès privé ; établissement d'un accès privé|  
|[Compilateur avertissement (niveau 4) C4435](../../error-messages/compiler-warnings/compiler-warning-level-4-c4435.md)|'derived_class' : la disposition des objets sous/vd2 change en raison de la base virtuelle « base_class »|  
|[Compilateur avertissement (niveau 1) C4436](../../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md)|dynamic_cast de la base virtuelle 'base_class' en 'derived_class' dans le constructeur ou un destructeur peut échouer avec un objet partiellement construit|  
|[Compilateur avertissement (niveau 4) C4437](../../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md)|dynamic_cast de la base virtuelle 'base_class' en 'derived_class' risque d’échouer dans certains contextes|  
|Avertissement C4438 du compilateur|'%$S' : ne peut pas être appelée en toute sécurité / await : mode de clrcompat. Si le CLR appelle « %$S », cela peut entraîner une altération de la tête de CLR|  
|[Avertissement du compilateur C4439](../../error-messages/compiler-warnings/compiler-warning-c4439.md)|'fonction' : définition de fonction avec un type managé dans la signature doit avoir une convention d’appel __clrcall|  
|[Compilateur avertissement (niveau 1) C4440](../../error-messages/compiler-warnings/compiler-warning-level-1-c4440.md)|appel de redéfinition de la convention de 'convention_appel1' à 'calling_convenction2' ignoré|  
|[Compilateur avertissement (niveau 1) C4441](../../error-messages/compiler-warnings/compiler-warning-level-1-c4441.md)|convention d’appel de 'convention_appel1' ignoré ; utilisé à la place de 'convention_appel2'|  
|Avertissement du compilateur (niveau 1) C4442|terminateur null incorporé dans un argument __annotation.  Valeur sera tronquée.|  
|Avertissement du compilateur (niveau 1) C4443|le paramètre pragma attendu doit être '0', '1' ou '2'|  
|Avertissement du compilateur (niveau 3) C4444|'identificateur' : '__unaligned' de niveau supérieur n’est pas implémenté dans ce contexte|  
|[Compilateur avertissement (niveau 1) C4445](../../error-messages/compiler-warnings/compiler-warning-level-1-c4445.md)|'fonction' : dans un « WinRT | gérés ' type d’une méthode virtuelle ne peut pas être privée|  
|Avertissement du compilateur (niveau 1) C4446|'%$S' : Impossible de mapper le membre ' % $I ' dans ce type, en raison de conflits avec le nom de type. La méthode a été renommée en ' % $I '|  
|Avertissement du compilateur (niveau 1) C4447|signature 'principale' trouvée sans le modèle de thread. Utilisez ' int main (Platform::Array\<Platform::String ^ > ^ args) ».|  
|Avertissement C4448 du compilateur|'%$S' n’a pas d’interface par défaut spécifiée dans les métadonnées. Prélèvement : '%$S, ce qui risque d’échouer lors de l’exécution.|  
|Avertissement C4449 du compilateur|'%$S un type doit être marqué comme '[WebHostHidden]'|  
|Avertissement C4450 du compilateur|'%$S' doit être marqué comme '[WebHostHidden]', car il dérive de '%$S'|  
|Avertissement du compilateur (niveau 4) C4451|'classname1::member' : utilisation de la classe ref 'classname2::member' dans ce contexte peut entraîner de marshaling non valide d’objet entre les contextes|  
|Avertissement du compilateur (niveau 1) C4452|'identificateur' : type public ne peut pas être portée globale. Il doit être dans un espace de noms qui est un enfant du nom du fichier de sortie .winmd.|  
|Avertissement du compilateur (niveau 1) C4453|'%$S' : un type « [WebHostHidden] » ne doit pas être utilisé sur la surface d’un type public qui n’est pas publiée '[WebHostHidden]'|  
|Avertissement du compilateur (niveau 1) C4454|'%$S' est surchargée par le nombre de paramètres d’entrée sans avoir [DefaultOverload] spécifié. Enlèvement '%$D' en tant que la surcharge par défaut|  
|Avertissement du compilateur (niveau 1) C4455|'operator %$I' : les identificateurs de suffixe littéral ne commençant pas par un trait de soulignement sont réservés|  
|Avertissement du compilateur (niveau 3) C4456|déclaration de 'identificateur' masque une déclaration locale précédente|  
|Avertissement du compilateur (niveau 3) C4457|déclaration de 'identificateur' masque le paramètre de fonction|  
|Avertissement du compilateur (niveau 3) C4458|déclaration de 'identificateur' masque le membre de classe|  
|Avertissement du compilateur (niveau 3) C4459|déclaration de 'identificateur' masque une déclaration globale|  
|[Compilateur avertissement (niveau 4) C4460](../../error-messages/compiler-warnings/compiler-warning-level-4-c4460.md)|« WinRT | gérés ' opérateur 'opérateur', a des paramètres passés par référence. « WinRT | gérés ' opérateur 'opérateur' a une sémantique différente de l’opérateur C++ 'cpp_operator', souhaitez-vous effectuer un passage par valeur ?|  
|[Compilateur avertissement (niveau 1) C4461](../../error-messages/compiler-warnings/compiler-warning-level-1-c4461.md)|'classname' : cette classe a un finaliseur ' ! finaliseur ' mais pas de destructeur ' ~ destructeur »|  
|[Compilateur avertissement (niveau 1) C4462](../../error-messages/compiler-warnings/compiler-warning-level-1-c4462.md)|'type' : Impossible de déterminer le GUID du type. Le programme risque d'échouer au moment de l'exécution.|  
|Avertissement C4463 du compilateur|dépassement de capacité ; affectation 'value' pour le champ de bits qui ne peut contenir que des valeurs comprises entre 'mi_valuen' et « max_value »|  
|Avertissement C4464 du compilateur|rapport inclut le chemin d’accès contient '..'|  
|[Compilateur avertissement (niveau 1) C4470](../../error-messages/compiler-warnings/compiler-warning-level-1-c4470.md)|pragmas de contrôle à virgule flottante ignorés sous /clr|  
|Avertissement du compilateur (niveau 4) C4471|'énumération' : une déclaration anticipée d’une énumération non délimitée doit avoir un type sous-jacent (int pris par défaut)|  
|Avertissement du compilateur (niveau 1) C4472|'identificateur' est un enum natif : ajoutez un spécificateur d’accès (public/privé) pour déclarer un ' WinRT | managé ' enum|  
|Avertissement C4480 du compilateur|extension non standard utilisée : spécification du type sous-jacent de l’enum 'énumération'|  
|[Compilateur avertissement (niveau 4) C4481](../../error-messages/compiler-warnings/compiler-warning-level-4-c4481.md)|extension non standard utilisée : 'mot clé' de spécificateur de substitution|  
|Avertissement C4482 du compilateur|extension non standard utilisée : enum 'énumération' utilisée dans le nom qualifié|  
|Avertissement du compilateur (niveau 1) C4483|erreur de syntaxe : mot clé C++ attendu|  
|[Avertissement du compilateur C4484](../../error-messages/compiler-warnings/compiler-warning-c4484.md)|'fonction_substitution' : correspond à la méthode de classe ref de base 'fonction_classe_base', mais n’est pas marquée 'virtual', 'new' ou 'override' ; 'new' (et non 'virtual') sont supposé.|  
|[Avertissement du compilateur C4485](../../error-messages/compiler-warnings/compiler-warning-c4485.md)|'fonction_substitution' : correspond à la méthode de classe ref de base 'fonction_classe_base', mais n’est pas marqué comme 'new' ou 'override' ; 'new' (et 'virtual') sont supposés.|  
|[Compilateur avertissement (niveau 1) C4486](../../error-messages/compiler-warnings/compiler-warning-level-1-c4486.md)|'fonction' : une méthode virtuelle privée d’une classe ref ou d’une classe value doit être marquée comme 'sealed'|  
|[Compilateur avertissement (niveau 4) C4487](../../error-messages/compiler-warnings/compiler-warning-level-4-c4487.md)|'fonction_classe_dérivée' : correspond à la méthode non virtuelle héritée 'fonction_classe_base' mais n’est pas explicitement marqué comme 'new'|  
|[Compilateur avertissement (niveau 1) C4488](../../error-messages/compiler-warnings/compiler-warning-level-1-c4488.md)|'fonction' : requiert le mot clé 'mot clé' pour implémenter la méthode d’interface 'méthode_interface'|  
|[Compilateur avertissement (niveau 1) C4489](../../error-messages/compiler-warnings/compiler-warning-level-1-c4489.md)|'spécificateur' : non autorisé sur la méthode d’interface 'méthode' ; remplacer spécificateurs sont autorisées uniquement sur les méthodes de classe de classe et la valeur ref|  
|[Compilateur avertissement (niveau 1) C4490](../../error-messages/compiler-warnings/compiler-warning-level-1-c4490.md)|'override' : utilisation incorrecte du spécificateur de substitution ; 'fonction' ne correspond pas à une méthode de classe ref de base|  
|Avertissement du compilateur (niveau 1) C4491|'%s' : format de version IDL non conforme|  
|Avertissement du compilateur (niveau 1) C4492|'%$S' : correspond à la méthode de classe ref '%$S', mais n'est pas marqué comme 'override'|  
|Avertissement du compilateur (niveau 3) C4493|expression de suppression n’a aucun effet car le destructeur de 'type' n’a pas d’accessibilité 'publique'|  
|Avertissement du compilateur (niveau 1) C4494|'%$S' : ignore __declspec(allocateur) car le type de retour de la fonction n'est pas un pointeur ni une référence|  
|[Compilateur avertissement (niveau 1) C4502](../../error-messages/compiler-warnings/compiler-warning-level-1-c4502.md)|'linkage specification' nécessite l'utilisation du mot clé 'extern' et doit précéder tous les autres spécificateurs|  
|[Erreur C4503 de compilateur avertissement (niveau 1)](../../error-messages/compiler-warnings/compiler-warning-level-1-c4503.md)|'identificateur' : longueur du nom dépassée, décoré nom a été tronqué.|  
|[Compilateur avertissement (niveau 4) C4505](../../error-messages/compiler-warnings/compiler-warning-level-4-c4505.md)|'fonction' : fonction locale non référencée a été supprimée.|  
|[Compilateur avertissement (niveau 1) C4506](../../error-messages/compiler-warnings/compiler-warning-level-1-c4506.md)|aucune définition de fonction inline 'fonction'|  
|[Compilateur avertissement (niveau 1) C4508](../../error-messages/compiler-warnings/compiler-warning-level-1-c4508.md)|'fonction' : fonction doit retourner une valeur ; type supposé de retour 'void'|  
|Avertissement C4509 du compilateur|extension non standard utilisée : 'fonction' utilise SEH et 'objet' a un destructeur|  
|[Compilateur avertissement (niveau 4) C4510](../../error-messages/compiler-warnings/compiler-warning-level-4-c4510.md)|'classe' : constructeur par défaut a été défini de manière implicite comme étant supprimé|  
|[Compilateur avertissement (niveau 3) C4511](../../error-messages/compiler-warnings/compiler-warning-level-3-c4511.md)|'classe' : le constructeur de copie a été défini de manière implicite comme étant supprimé|  
|[Compilateur (niveau 4) d’avertissement C4512](../../error-messages/compiler-warnings/compiler-warning-level-4-c4512.md)|'classe' : l’opérateur d’assignation a été défini de manière implicite comme étant supprimé|  
|[Compilateur avertissement (niveau 4) C4513](../../error-messages/compiler-warnings/compiler-warning-level-4-c4513.md)|'classe' : destructeur a été défini de manière implicite comme étant supprimé|  
|[Compilateur avertissement (niveau 4) C4514](../../error-messages/compiler-warnings/compiler-warning-level-4-c4514.md)|'fonction' : la fonction inline non référencée a été supprimée|  
|[Compilateur avertissement (niveau 4) C4515](../../error-messages/compiler-warnings/compiler-warning-level-4-c4515.md)|'namespace' : espace de noms s’utilise lui-même|  
|[Compilateur avertissement (niveau 4) C4516](../../error-messages/compiler-warnings/compiler-warning-level-4-c4516.md)|'class::symbol' : les déclarations access sont déconseillées ; les déclarations à l’aide de membre constituent une meilleure alternative|  
|[Compilateur avertissement (niveau 4) C4517](../../error-messages/compiler-warnings/compiler-warning-level-4-c4517.md)|les déclarations d'accès sont déconseillées ; les déclarations using de membres constituent un meilleur choix|  
|[Compilateur avertissement (niveau 1) C4518](../../error-messages/compiler-warnings/compiler-warning-level-1-c4518.md)|'spécificateur' : classe de stockage ou de type inattendu ; ignoré|  
|Avertissement C4519 du compilateur|arguments template par défaut autorisés uniquement sur un modèle de classe|  
|[Compilateur avertissement (niveau 3) C4521](../../error-messages/compiler-warnings/compiler-warning-level-3-c4521.md)|'classe' : plusieurs constructeurs de copie spécifiés|  
|[Compilateur avertissement (niveau 3) C4522](../../error-messages/compiler-warnings/compiler-warning-level-3-c4522.md)|'classe' : plusieurs opérateurs d’assignation spécifiés|  
|[Compilateur avertissement (niveau 3) C4523](../../error-messages/compiler-warnings/compiler-warning-level-3-c4523.md)|'classe' : plusieurs destructeurs spécifiés|  
|[Compilateur avertissement (niveau 1) C4526](../../error-messages/compiler-warnings/compiler-warning-level-1-c4526.md)|'fonction' : fonction membre static ne peuvent pas remplacer la fonction virtuelle 'fonction_virtuelle' \n substitution ignorée, la fonction virtual sera masquée|  
|[Compilateur avertissement (niveau 1) C4530](../../error-messages/compiler-warnings/compiler-warning-level-1-c4530.md)|Gestionnaire d’exceptions C++ utilisé, mais les sémantiques de déroulement ne sont pas activées. Spécifiez /EHsc|  
|Avertissement du compilateur (niveau 1) C4531|Gestion des exceptions C++ non disponible sous Windows CE. Utilisez la gestion structurée des exceptions|  
|[Compilateur avertissement (niveau 1) C4532](../../error-messages/compiler-warnings/compiler-warning-level-1-c4532.md)|'continue' : sortie bloc ' __finally/finally' a un comportement indéfini lors de la gestion de l’arrêt|  
|[Compilateur avertissement (niveau 1) C4533](../../error-messages/compiler-warnings/compiler-warning-level-1-c4533.md)|l’initialisation de 'variable' est ignorée par 'étiquette goto'|  
|[Compilateur avertissement (niveau 3) C4534](../../error-messages/compiler-warnings/compiler-warning-level-3-c4534.md)|'constructeur' ne sera pas un constructeur par défaut pour ' classe | struct' 'identificateur' en raison de l’argument par défaut|  
|[Compilateur avertissement (niveau 3) C4535](../../error-messages/compiler-warnings/compiler-warning-level-3-c4535.md)|appel de _set_se_translator() requiert /EHa|  
|[Compilateur avertissement (niveau 4) C4536](../../error-messages/compiler-warnings/compiler-warning-level-4-c4536.md)|'NomType' : nom de type dépasse la limite métadonnées de 'character_limit' caractères|  
|[Compilateur avertissement (niveau 1) C4537](../../error-messages/compiler-warnings/compiler-warning-level-1-c4537.md)|'objet' : '.' appliqué à un type non UDT|  
|[Compilateur avertissement (niveau 3) C4538](../../error-messages/compiler-warnings/compiler-warning-level-3-c4538.md)|'type' : les qualificateurs const/volatile pour ce type ne sont pas pris en charge.|  
|[Compilateur avertissement (niveau 1) C4540](../../error-messages/compiler-warnings/compiler-warning-level-1-c4540.md)|utilisé de dynamic_cast pour convertir en base ambiguë ou inaccessible ; test d’exécution échouera ('type1' en 'type2')|  
|[Compilateur avertissement (niveau 1) C4541](../../error-messages/compiler-warnings/compiler-warning-level-1-c4541.md)|'identificateur' utilisé sur un type polymorphe 'type' avec/GR ; un comportement imprévisible|  
|Avertissement du compilateur (niveau 1) C4542|Génération ignorée du fichier texte injecté fusionné, impossible d'écrire le fichier %$M : '%s' : %$e|  
|[Compilateur avertissement (niveau 3) C4543](../../error-messages/compiler-warnings/compiler-warning-level-3-c4543.md)|Texte injecté supprimé par l'attribut 'no_injected_text'|  
|[Compilateur avertissement (niveau 1) C4544](../../error-messages/compiler-warnings/compiler-warning-level-1-c4544.md)|'déclaration' : argument de modèle ignoré sur cette déclaration de modèle par défaut|  
|[Compilateur avertissement (niveau 1) C4545](../../error-messages/compiler-warnings/compiler-warning-level-1-c4545.md)|l’expression avant la virgule correspond à une fonction qui n’a pas de liste d’arguments|  
|[Compilateur avertissement (niveau 1) C4546](../../error-messages/compiler-warnings/compiler-warning-level-1-c4546.md)|l’appel de fonction avant la virgule n’a pas de liste d’arguments|  
|[Compilateur avertissement (niveau 1) C4547](../../error-messages/compiler-warnings/compiler-warning-level-1-c4547.md)|'opérateur' : l'opérateur avant la virgule n'a pas d'effet ; opérateur avec effet secondaire attendu|  
|[Compilateur avertissement (niveau 1) C4548](../../error-messages/compiler-warnings/compiler-warning-level-1-c4548.md)|l'expression avant la virgule n'a pas d'effet ; expression avec effet secondaire attendu|  
|[Compilateur avertissement (niveau 1) C4549](../../error-messages/compiler-warnings/compiler-warning-level-1-c4549.md)|'opérateur' : l'opérateur avant la virgule n'a pas d'effet ; souhaitez-vous utiliser 'opérateur' ?|  
|[Compilateur avertissement (niveau 1) C4550](../../error-messages/compiler-warnings/compiler-warning-level-1-c4550.md)|l'expression évalue une fonction dans laquelle manque une liste d'arguments|  
|[Compilateur avertissement (niveau 1) C4551](../../error-messages/compiler-warnings/compiler-warning-level-1-c4551.md)|liste d'arguments manquante dans l'appel de fonction|  
|[Compilateur avertissement (niveau 1) C4552](../../error-messages/compiler-warnings/compiler-warning-level-1-c4552.md)|'opérateur' : opérateur n’a aucun effet ; opérateur avec effet secondaire attendu|  
|[Compilateur avertissement (niveau 1) C4553](../../error-messages/compiler-warnings/compiler-warning-level-1-c4553.md)|'opérateur' : opérateur n’a aucun effet ; souhaitez-vous utiliser ' opérateur ?|  
|[Compilateur avertissement (niveau 3) C4554](../../error-messages/compiler-warnings/compiler-warning-level-3-c4554.md) C4554|'opérateur' : Vérifiez la priorité des opérateurs d’erreur possibles ; Utilisez des parenthèses pour clarifier la priorité|  
|[Compilateur avertissement (niveau 1) C4555](../../error-messages/compiler-warnings/compiler-warning-level-1-c4555.md)|l'expression n'a pas d'effet ; attendue expression avec effets secondaires|  
|[Compilateur avertissement (niveau 1) C4556](../../error-messages/compiler-warnings/compiler-warning-level-1-c4556.md)|valeur d’argument immédiat intrinsèque 'valeur' est hors limites » lower_bound - upper_bound »|  
|[Compilateur avertissement (niveau 3) C4557](../../error-messages/compiler-warnings/compiler-warning-level-3-c4557.md)|'__assume' contient l'effet 'effet'|  
|[Compilateur avertissement (niveau 1) C4558](../../error-messages/compiler-warnings/compiler-warning-level-1-c4558.md)|valeur d’opérande 'valeur' est hors limites » lower_bound - upper_bound »|  
|[Compilateur avertissement (niveau 4) C4559](../../error-messages/compiler-warnings/compiler-warning-level-4-c4559.md)|'fonction' : redéfinition ; la fonction gagne __declspec (modifier)|  
|[Compilateur avertissement (niveau 1) C4561](../../error-messages/compiler-warnings/compiler-warning-level-1-c4561.md)|'__fastcall' incompatible avec le « / clr' option : conversion en '\__stdcall »|  
|Avertissement du compilateur (niveau 4) C4562|les fonctions entièrement prototypées sont requises avec l'option '/clr' : conversion de '()' en '(void)'|  
|[Compilateur avertissement (niveau 4) C4564](../../error-messages/compiler-warnings/compiler-warning-level-4-c4564.md)|la méthode 'méthode' de 'classe' 'classname' définit un paramètre non pris en charge par défaut 'paramètre'|  
|[Compilateur avertissement (niveau 4) C4565](../../error-messages/compiler-warnings/compiler-warning-level-4-c4565.md)|'fonction' : redéfinition ; le symbole était déclaré précédemment avec __declspec (modifier)|  
|[Compilateur avertissement (niveau 1) C4566](../../error-messages/compiler-warnings/compiler-warning-level-1-c4566.md)|caractère représenté par le nom de caractère universel 'char' ne peut pas être représenté dans la page de codes actuelle (%d)|  
|Avertissement du compilateur (niveau 1) C4568|'%$S' : aucun membre ne correspond à la signature de la substitution explicite|  
|Avertissement du compilateur (niveau 3) C4569|'%$S' : aucun membre ne correspond à la signature de la substitution explicite|  
|[Compilateur avertissement (niveau 3) C4570](../../error-messages/compiler-warnings/compiler-warning-level-3-c4570.md)|'type' : n’est pas explicitement déclaré comme abstract mais comporte des fonctions abstract|  
|[Compilateur avertissement (niveau 4) C4571](../../error-messages/compiler-warnings/compiler-warning-level-4-c4571.md)|Informations : la sémantique catch(...) a changé depuis Visual C++ 7.1 ; les exceptions structurées (SEH) ne sont plus interceptées|  
|[Compilateur avertissement (niveau 1) C4572](../../error-messages/compiler-warnings/compiler-warning-level-1-c4572.md)|L’attribut [ParamArray] est déconseillé sous/CLR, utilisez '...' à la place|  
|Avertissement du compilateur (niveau 1) C4573|l'utilisation de '%$S' exige que le compilateur capture 'this', ce qui n'est pas autorisé par le mode de capture par défaut actuel|  
|Avertissement du compilateur (niveau 4) C4574|'Identificateur' est défini comme étant '0' : voulez-vous utiliser 'identifier #if' ?|  
|Avertissement du compilateur (niveau 1) C4575|'__vectorcall' incompatible avec le « / clr' option : conversion en '\__stdcall »|  
|[Compilateur avertissement (niveau 3) C4580](../../error-messages/compiler-warnings/compiler-warning-level-3-c4580.md)|[attribute] est déconseillé ; spécifiez System::Attribute ou Platform::Metadata comme classe de base à la place|  
|[Compilateur avertissement (niveau 1) C4581](../../error-messages/compiler-warnings/compiler-warning-level-1-c4581.md)|comportement désapprouvé : '« string »' remplacé par 'chaîne' pour traiter l’attribut|  
|Avertissement du compilateur (niveau 4) C4582|'%$S' : le constructeur n'est pas appelé de manière implicite|  
|Avertissement du compilateur (niveau 4) C4583|'%$S' : le destructeur n'est pas appelé de manière implicite|  
|[Compilateur avertissement (niveau 1) C4584](../../error-messages/compiler-warnings/compiler-warning-level-1-c4584.md)|'classe1' : classe de base 'classe2' est déjà une classe de base de « % class3 »|  
|Avertissement du compilateur (niveau 1) C4585|'classe' : un WinRT 'classe ref publique' doit être scellée ou dérive d’existant non scellés (classe)|  
|Avertissement du compilateur (niveau 1) C4586|'%$S' : un type public ne peut pas être déclaré dans un espace de noms de niveau supérieur appelé 'Windows'|  
|Avertissement du compilateur (niveau 1) C4587|'anonymous_structure' : changement de comportement : n’est plus implicitement appelé|  
|Avertissement du compilateur (niveau 1) C4588|'anonymous_structure' : changement de comportement : destructeur est appelé n’est plus implicitement.|  
|Avertissement du compilateur (niveau 1) C4591|limites de dépassé la profondeur des appels 'constexpr' (/ constexpr:depth\<nombre >)|  
|Avertissement du compilateur (niveau 3) C4592|'fonction' : 'constexpr' appeler d’évaluation a échoué ; fonction est appelée au moment de l’exécution|  
|Avertissement du compilateur (niveau 1) C4593|'fonction' : limite d’étape d’évaluation d’appels 'constexpr' de 'limite' dépassé ; Utilisez /constexpr:steps\<nombre > pour augmenter la limite|  
|Avertissement du compilateur (niveau 3) C4594|'%$S' : le destructeur ne sera pas appelé de manière implicite si une exception est levée|  
|Avertissement du compilateur (niveau 1) C4595|'%$S' : changement de comportement : le destructeur ne sera plus appelé de manière implicite si une exception est levée|
