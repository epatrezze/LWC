# LWC

// miscMultipleTemplates.js

import { LightningElement } from 'lwc';
import templateOne from './templateOne.html';
import templateTwo from './templateTwo.html';

export default class MiscMultipleTemplates extends LightningElement {

    templateOne = true;

    render() {
         if(templateOne)
             return templateOne;
         else
             return templateTwo;

    }

    switchTemplate(){ 
        if(this.templateOne === true)
            this.templateOne = false;
        else
            this.templateOne = true; 
    }
} 
