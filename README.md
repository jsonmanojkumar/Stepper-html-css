# Stepper-html
        <div class="wrapper-progressBar">
          <ul class="progressBar">
            <li class="{{item.checked}}" *ngFor="let item of stap">
              <span>{{item.name}}</span>
            </li>
          </ul>
        </div>


        <ion-button (click)="testAlert1()">1</ion-button>
        <ion-button (click)="testAlert2()">2</ion-button>
        <ion-button (click)="testAlert3()">3</ion-button>
        <ion-button (click)="testAlert4()">4</ion-button>

# Stepper-CSS

        .wrapper-progressBar {
      width: 100%
    }

    .progressBar {
      counter-reset: step;
      display: flex;
      justify-content: start;
    }

    .progressBar li span {
      font-size: 14px;
      font-weight: 500;
      text-align: center;
    }

    .progressBar li {
      list-style-type: none;
      float: left;
      width: 21%;
      position: relative;
      text-align: center;
      font-weight: bold;
    }

    .progressBar li:before {
      cursor: pointer;

      /* content:'✔'; */
      content: counter(step);
      counter-increment: step;

      line-height: 30px;
      border-radius: 50%;
      width: 30px;
      height: 30px;
      border: 1px solid #ddd;
      display: block;
      text-align: center;
      margin: 0 auto 10px;
      color: white;
      background-color:rgb(98 98 98)
    }

    .progressBar li:after {
      content: "";
      position: absolute;
      width: 100%;
      height: 2px;
      background-color: #d1d1d1;
      top: 15px;
      left: -50%;
      z-index: -1;
    }

    .progressBar li:first-child:after {
      content: none;

    }

    .progressBar li.active {
      color: green;
    }

    .progressBar li.active:before {
      border-color: rgb(23, 194, 23);
      background-color: rgb(13, 141, 34);
      color: white;
      content: '✔';
    }

    .progressBar li.active+li:after {
      background-color: rgb(196, 196, 196);
    }



# Stepper-TS


         stap = [
            { id: 'step1', name: 'item1', checked: 'active' },
            { id: 'step2', name: 'item2', checked: '' },
            { id: 'step3', name: 'item3', checked: '' },
            { id: 'step4', name: 'item4', checked: '' }
          ]
        
          testAlert1() {
            this.stap[0].checked = 'deactive';
          }
          testAlert2() {
            this.stap[1].checked = 'active';
          }
          testAlert3() {
            this.stap[2].checked = 'deactive';
          }
          testAlert4() {
            this.stap[3].checked = 'active';
          }

