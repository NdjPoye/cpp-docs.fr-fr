---
layout: LandingPage
title: "Accès aux données dans Visual C++"
translationtype: Human Translation
ms.sourcegitcommit: f9e63f47a8df69b52a6a12688e84602981d20dae
ms.openlocfilehash: 807cf772d632f66f74a210985ff611fc31ee594a
ms.lasthandoff: 03/21/2017

---
# <a name="data-access-in-visual-c"></a>Accès aux données dans Visual C++

Pratiquement tous les produits de base de données, SQL et NoSQL, fournissent une interface pour les applications C++ natives. L’interface standard du secteur est ODBC, qui est prise en charge par tous les principaux produits de base de données SQL et de nombreux produits NoSQL. Pour les produits non-Microsoft, contactez le fournisseur pour plus d’informations. Des bibliothèques tierces avec différents contrats de licence sont également disponibles.

Depuis 2011, Microsoft s’est aligné sur ODBC en tant que standard pour les applications natives se connectant aux bases de données Microsoft SQL Server, localement et dans le cloud. Pour plus d’informations, consultez [Programmation de l’accès aux données \(MFC-ATL\)](data-access-programming-mfc-atl.md). Les bibliothèques C++/CLI peuvent utiliser les pilotes ODBC natifs ou ADO.NET. Pour plus d’informations, consultez [Accès aux données à l’aide d’ADO.NET (C++/CLI)](/dotnet/data-access-using-adonet-cpp-cli.md) et [Accès aux données dans Visual Studio](https://docs.microsoft.com/visualstudio/data-tools/accessing-data-in-visual-studio).

<ul class="panelContent cardsF">
<li>
        <a href="/azure/sql-database/sql-database-develop-cplusplus-simple">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/azure/media/index/SQLDatabase.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>Se connecter à la base de données SQL à l’aide de C et C++</h3>
                        <p>Se connecter à Azure SQL Database à partir d’applications C ou C++</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://github.com/Azure/azure-storage-cpp">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/azure/media/index/Storage.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>Bibliothèque cliente de stockage Microsoft Azure pour C++</h3>
                        <p>Le service [Stockage Azure](/azure/storage/storage-introduction) est une solution de stockage cloud pour les applications modernes qui s’appuient sur la durabilité, la disponibilité et la scalabilité afin de répondre aux besoins de leurs clients. Connectez-vous au service Stockage Azure à partir de C++ à l’aide de la bibliothèque cliente de stockage Azure pour C++.</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://blogs.msdn.microsoft.com/sqlnativeclient/2016/08/01/announcing-the-odbc-driver-13-1-for-sql-server/">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_drivers.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>Pilote ODBC 13.1 pour SQL Server, publication de Windows</h3>
                        <p>Le dernier pilote ODBC fournit un accès fiable aux données de Microsoft SQL Server 2016 et Microsoft Azure SQL Database pour les applications C/C++. Assure la prise en charge des fonctionnalités comme Always Encrypted, Azure Active Directory et les groupes de disponibilité AlwaysOn. Également disponible pour Mac OS et Linux.</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://msdn.microsoft.com/library/ms130892.aspx">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_api.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>SQL Server Native Client</h3>
                        <p>SQL Server Native Client est une interface de programmation d’application (API) d’accès aux données autonome, utilisée pour OLE DB et ODBC, qui prend en charge les versions SQL Server 2005 à SQL Server 2014. Les nouvelles applications doivent utiliser le pilote ODBC 13.1 pour SQL Server.</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="data-access-programming-mfc-atl.md">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_api.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>Programmation de l'accès aux données</h3>
                        <p>Décrit la programmation de l'accès aux données héritées avec Visual C++, où la meilleure méthode consiste à utiliser l'une des bibliothèques de classes telles que la bibliothèque ATL (Active Template Library) ou la bibliothèque MFC (Microsoft Foundation Class), qui simplifient l'utilisation des API de base de données.</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="odbc/open-database-connectivity-odbc.md">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_multi-connect.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>ODBC (Open Database Connectivity)</h3>
                        <p>La bibliothèque Microsoft Foundation Classes (MFC) fournit des classes pour la programmation avec Open Database Connectivity (ODBC).</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="oledb/ole-db-programming.md">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_generic-database.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>Programmation OLE DB</h3>
                        <p>Fournit des liens vers des rubriques conceptuelles traitant de la technologie de base de données OLE DB et de la bibliothèque de modèles OLE DB. (OLE DB n’est pas recommandée pour les nouvelles applications, sauf dans les scénarios impliquant des serveurs liés.)</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    
</ul>

---

<h2>Référence</h2>

<ul class="panelContent cardsW">
 <li>
        <a href="https://azure.microsoft.com/develop/cpp/">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3>Centre de développement Microsoft Azure C et C++</h3>
                        <p>Azure facilite la création d’applications C++ avec plus de souplesse, de scalabilité et de fiabilité à l’aide des outils que vous aimez.</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/azure/storage/storage-c-plus-plus-how-to-use-blobs">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3>Guide pratique pour utiliser le stockage Blob à partir de C++</h3>
                        <p>Le stockage Blob Azure est un service qui stocke les données non structurées dans le cloud en tant qu’objets/objets blob. Le stockage Blob permet de stocker n’importe quel type de données texte ou binaires, par exemple un document, un fichier multimédia ou un programme d’installation d’application. Le stockage Blob est également appelé stockage d’objets.</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/sql/odbc/reference/odbc-programmer-s-reference">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3>Guide de référence du programmeur ODBC</h3>
                        <p>L’interface ODBC est conçue pour une utilisation avec le langage de programmation C. L’utilisation de l’interface ODBC s’étend sur trois domaines : les instructions SQL, les appels de fonctions ODBC et la programmation en C.</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3><a href="https://www.microsoft.com/download/details.aspx?id=53339" title="Microsoft® ODBC Driver 13.1 for SQL Server® - Windows Download Page">Pilote ODBC 13.1 pour SQL Server</a></h3>
                        <p>Le pilote Microsoft ODBC 13.1 pour SQL Server est une bibliothèque de liens dynamiques (DLL) qui prend en charge le runtime des applications par le biais d’API de code natif qui permettent d’établir la connexion à Microsoft SQL Server 2008, SQL Server 2008 R2, SQL Server 2012, SQL Server 2016, Analytics Platform System, Azure SQL Database et Azure SQL Data Warehouse. Téléchargez le pilote ici.</p>
                    </div>
                </div>
            </div>
        </div>        
    </li>
    
</ul>
