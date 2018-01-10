---
title: "-exécution-jeu de caractères (jeu de caractères d’exécution de jeu) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- execution-charset
- /execution-charset
dev_langs: C++
helpviewer_keywords:
- /execution-charset compiler option
- -execution-charset compiler option
ms.assetid: 0e02f487-2236-45bc-95f3-5760933a8f96
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7cfb315c0dece0edc6228f70ed3900be80543cc7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="execution-charset-set-execution-character-set"></a>/ EXECUTION-CharSet (définir l’exécution du jeu de caractères)
Permet de spécifier l’exécution du jeu de caractères pour votre fichier exécutable.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/execution-charset:[IANA_name|.CPID]  
```  
  
## <a name="arguments"></a>Arguments  
 **IANA_name**  
 Nom du jeu de caractères définis par l’IANA.  
  
 **CPID**  
 Identificateur de la page de codes.  
  
## <a name="remarks"></a>Notes  
 Vous pouvez utiliser la **/Execution-CharSet** permettant de spécifier un jeu de caractères d’exécution. Le jeu de caractères d’exécution est l’encodage utilisé pour le texte de votre programme est entrée dans la phase de compilation une fois toutes les étapes de prétraitement. Ce jeu de caractères est utilisé pour la représentation interne de littéraux chaîne ou un caractère dans le code compilé. Définissez cette option pour spécifier le jeu de caractères d’exécution étendu à utiliser lors de vos fichiers sources incluent les caractères qui ne sont pas représentables dans le jeu de caractères d’exécution de base. Vous pouvez utiliser soit l’IANA ou nom de jeu de caractères ISO, ou un point (.) suivi d’un identificateur de page de code décimal de 3 à 5 chiffres pour spécifier le jeu de caractères à utiliser. Pour une liste de prise en charge les identificateurs de page de code et les noms de jeu de caractères, consultez [Code Page Identifiers](http://msdn.microsoft.com/library/windows/desktop/dd317756).  
  
 Par défaut, Visual Studio détecte une marque d’ordre d’octet pour déterminer si le fichier source est encodé au format Unicode, par exemple, UTF-16 ou UTF-8. Si aucune marque d’ordre d’octet n’est trouvé, il suppose que le fichier source est encodé à l’aide de la page de code utilisateur actuel, sauf si vous avez spécifié un jeu de caractères nom ou page de codes à l’aide de la **/source-CharSet** option ou   **/UTF-8** option. Visual Studio vous permet d’enregistrer votre code source C++ à l’aide de plusieurs codages de caractères. Pour plus d’informations sur les jeux de caractères source et de l’exécution, consultez [jeux de caractères](../../cpp/character-sets2.md) dans la documentation de langage.  
  
 Si vous souhaitez définir le jeu de caractères source et le jeu de caractères d’exécution au format UTF-8, vous pouvez utiliser la **/UTF-8** option du compilateur en guise de raccourci. Il revient à spécifier **/source-charset:utf-/execution 8-charset:utf-8** sur la ligne de commande. Une de ces options également permet la **/Validate-CharSet** option par défaut.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Pour définir cette option du compilateur dans l’environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriétés** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Développez le **propriétés de Configuration**, **C/C++**, **ligne de commande** dossier.  
  
3.  Dans **Options avancées**, ajoutez le **/Execution-CharSet** option, puis spécifiez votre encodage préféré.  
  
4.  Choisissez **OK** pour enregistrer vos modifications.  
  
## <a name="see-also"></a>Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des Options du compilateur](../../build/reference/setting-compiler-options.md)   
 [/ source-CharSet (définir Source Character Set)](../../build/reference/source-charset-set-source-character-set.md)   
 [/ UTF-8 (définir la Source et le fichier exécutable jeux de caractères UTF-8)](../../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)   
 [/ Validate-CharSet (valider les caractères compatibles)](../../build/reference/validate-charset-validate-for-compatible-characters.md)