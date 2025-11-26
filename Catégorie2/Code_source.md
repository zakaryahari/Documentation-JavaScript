//Catégorie 2 : Manipulation du DOM

//Sélection d'Éléments

//### Définition :

Les fonctions de sélection d'éléments sont cruciales pour établir une référence entre le code JavaScript et les balises HTML.
    Elles permettent de cibler des éléments spécifiques du Document Object Model (DOM) pour pouvoir les manipuler.

//### Syntaxe :

document.getElementById('ID_UNIQUE');
    document.querySelector('.classe_ou_balise');
    document.querySelectorAll('.classe_ou_balise');

//Cas d'Utilisation :

--getElementById : Utilisé pour sélectionner un élément par son attribut id. C'est la méthode la plus rapide.
    const experiences_container = document.getElementById('experiences_container');

--querySelector : Utilisé pour sélectionner le premier élément qui correspond à un sélecteur CSS (classe, balise, ID).
    const add_employee_btn = document.querySelector('.Add-new-employee');

--querySelectorAll : Utilisé pour sélectionner tous les éléments qui correspondent à un sélecteur CSS. Elle retourne une NodeList.
    const companyInputs = document.querySelectorAll('.exp_company_input');

//Gestion des Événements

//### Définition :

La gestion des événements permet au code JavaScript de réagir aux interactions de l'utilisateur (clics, saisie de texte, etc.) ou aux changements du navigateur.

//### Syntaxe :

element.addEventListener(type_evenement, fonction_a_executer);

//Cas d'Utilisation :

--addEventListener : Attache un gestionnaire d'événement à l'élément spécifié.

--Événements courants : click : Se déclenche lorsque l'utilisateur clique sur l'élément.
    add_employee_btn.addEventListener('click', () => {
        Add_new_employee_form_container.classList.toggle('hidden');
    });

--Événements courants : input : Se déclenche à chaque modification de la valeur d'un champ de formulaire.
    add_employee_form.addEventListener('input', (e) => {
        const element_input = e.target;
        if (element_input.id === 'employee_nom_input') {
            Valide_input_regex(element_input, nom_regex, nom_spanId, nom_msg_error);
        }
    });

--Comportement par Défaut : Pour empêcher l'action par défaut du navigateur (comme recharger la page lors de la soumission d'un formulaire), on utilise la méthode preventDefault() sur l'objet événement.
    document.getElementById('employee_save_input').addEventListener('click', (e) => {
        // e.preventDefault(); // Nécessaire si le bouton était de type submit
        Valide_input_submit();
    });

//---

//Création/Modification d'Éléments

//### Définition :

Ces méthodes permettent de construire et de modifier dynamiquement la structure HTML du document (le DOM) en injectant ou en manipulant des balises.

//### Syntaxe :

document.createElement('div');
    parent.appendChild(enfant);
    element.innerHTML = 'Nouveau Contenu';

//Cas d'Utilisation :

--createElement : Crée un nouvel élément (moins utilisé dans les exemples ci-dessous, car l'injection de chaîne de caractères est privilégiée pour la rapidité).

--innerHTML : Permet de définir ou de remplacer le contenu HTML d'un élément. C'est idéal pour vider un conteneur ou injecter de grands blocs de code.
    // Utilisé pour vider le conteneur des employés non assignés avant de le mettre à jour.
    const All_Employee_List = document.getElementById('Display_Employee_list');
    All_Employee_List.innerHTML = '';

--insertAdjacentHTML / Concatenation += : Utilisé pour ajouter du HTML sans écraser le contenu existant. Ceci est utilisé pour insérer de nouveaux blocs d'expérience ou de nouveaux employés.
    // Fonction Add_employee_experience pour ajouter un nouveau champ d'expérience
    experiences_container.insertAdjacentHTML('beforeend', element_child);

// Fonction Display_Employee_list_SideBar pour ajouter un employé
    All_Employee_List.innerHTML += '<div class="list-employee" id=${employee.id}></div>';

.
