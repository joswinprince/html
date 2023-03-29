html
```
<div class="tree-box box-border">
  <ul class="trees">
    <li class="has-child">
      <input id="tree-controll1" type="checkbox" checked><span class="tree-control"></span>
      <label>
        <input type="checkbox" />
        <i class="fa fa-desktop light-blue"></i> Portail Gestionnaire main d'oeuvre (RPOP)
      </label>
      <ul>
        <li class="has-child">
          <input type="checkbox" checked><span class="tree-control"></span>
          <label>
            <input type="checkbox" />
            <i class="fa fa-tasks orange"></i> Administration des accès
          </label>
          <ul>
            <li>
              <label>
                <input type="checkbox" />
                <i class="fa fa-file "></i> Gérer les profils
              </label>
            </li>
            <li>
              <label>
                <input type="checkbox" checked/>
                <i class="fa fa-file "></i> Gérer les modules
              </label>
            </li>
            <li>
              <label>
                <input type="checkbox" checked/>
                <i class="fa fa-file "></i> Gérer les délégations
              </label>
            </li>
            <li>
              <label>
                <input type="checkbox" />
                <i class="fa fa-file "></i> Gérer les utilisateurs
              </label>
            </li>
            <li>
              <label>
                <input type="checkbox" checked/>
                <i class="fa fa-file "></i> Déclarer les PO
              </label>
            </li>

          </ul>
        </li>

        <li class="has-child">
          <input type="checkbox" checked><span class="tree-control"></span>
          <label>
            <input type="checkbox" />
            <i class="fa fa-tasks orange"></i> Gestion opérationnelle du périmètre
          </label>
          <ul>
            <li>
              <label>
                <input type="checkbox" />
                <i class="fa fa-file "></i> Gérer les PO
              </label>
            </li>
            <li>
              <label>
                <input type="checkbox" checked/>
                <i class="fa fa-file "></i> Gérer les favoris
              </label>
            </li>
            <li>
              <label>
                <input type="checkbox" checked/>
                <i class="fa fa-file "></i> Fiche du PO
              </label>
            </li>

          </ul>
        </li>
      </ul>
    </li>
    <li class="has-child">
      <input id="tree-controll2" type="checkbox" checked><span class="tree-control"></span>
      <label>
        <input type="checkbox" />
        <i class="fa fa-desktop light-blue"></i> Portail Gestionnaire main d'oeuvre (RPOP)
      </label>
      <ul>
        <li class="has-child">
          <input type="checkbox" checked><span class="tree-control"></span>
          <label>
            <input type="checkbox" />
            <i class="fa fa-tasks orange"></i> Administration des accès
          </label>
          <ul>
            <li>
              <label>
                <input type="checkbox" />
                <i class="fa fa-file "></i> Gérer les profils
              </label>
            </li>
            <li>
              <label>
                <input type="checkbox" checked/>
                <i class="fa fa-file "></i> Gérer les modules
              </label>
            </li>
            <li>
              <label>
                <input type="checkbox" checked/>
                <i class="fa fa-file "></i> Gérer les délégations
              </label>
            </li>
            <li>
              <label>
                <input type="checkbox" />
                <i class="fa fa-file "></i> Gérer les utilisateurs
              </label>
            </li>
            <li>
              <label>
                <input type="checkbox" checked/>
                <i class="fa fa-file "></i> Déclarer les PO
              </label>
            </li>

          </ul>
        </li>

        <li class="has-child">
          <input type="checkbox" checked><span class="tree-control"></span>
          <label>
            <input type="checkbox" />
            <i class="fa fa-tasks orange"></i> Gestion opérationnelle du périmètre
          </label>
          <ul>
            <li>
              <label>
                <input type="checkbox" />
                <i class="fa fa-file "></i> Gérer les PO
              </label>
            </li>
            <li>
              <label>
                <input type="checkbox" checked/>
                <i class="fa fa-file "></i> Gérer les favoris
              </label>
            </li>
            <li>
              <label>
                <input type="checkbox" checked/>
                <i class="fa fa-file "></i> Fiche du PO
              </label>
            </li>

          </ul>
        </li>
      </ul>
    </li>
  </ul>
</div>
```

css
```
ul,
li {
  list-style: none;
  margin: 0;
  padding: 0
}
label{font-weight:normal}
/*Tree*/

.trees {
  margin-left: 10px;
}

.trees li {
  border-left: dotted 1px #bcbec0;
  padding: 1px 0 1px 25px;
  position: relative
}

.trees li > label {
  position: relative;
  left: -11px
}

.trees li:before {
  content: "";
  width: 13px;
  height: 1px;
  border-bottom: dotted 1px #bcbec0;
  position: absolute;
  top: 10px;
  left: 0
}

.trees li:last-child:after {
  content: "";
  position: absolute;
  width: 2px;
  height: 13px;
  background: #fff;
  left: -1px;
  bottom: 0px;
}

.trees li input {
  margin-right: 5px;
  margin-left: 5px
}

.trees li.has-child > ul {
  display: none
}

.trees li.has-child > input {
  opacity: 0;
  position: absolute;
  left: -14px;
  z-index: 9999;
  width: 22px;
  height: 22px;
  top: -5px
}

.trees li.has-child > input + .tree-control {
  position: absolute;
  left: -4px;
  top: 6px;
  width: 8px;
  height: 8px;
  line-height: 8px;
  z-index: 2;
  display: inline-block;
  color: #fff;
  border-radius: 3px;
}

.trees li.has-child > input + .tree-control:after {
  font-family: 'FontAwesome';
  content: "";
  font-size: 8px;
  color: #183955;
  position: absolute;
  left: 1px
}

.trees li.has-child > input:checked + .tree-control:after {
  font-family: 'FontAwesome';
  content: "";
  font-size: 8px;
  color: #183955;
  position: absolute;
  left: 1px
}

.trees li.has-child > input:checked ~ ul {
  display: block
}

.trees ul li.has-child:last-child {
  border-left: none
}

.trees ul li.has-child:nth-last-child(2):after {
  content: "";
  width: 1px;
  height: 5px;
  border-left: dotted 1px #bcbec0;
  position: absolute;
  bottom: -5px;
  left: -1px
}

.tree-alt li {
  padding: 4px 0
}
```
