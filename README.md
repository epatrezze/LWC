# LWC


```
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

###template###

<template>
    <div class="container">

        <template if:true={firstAtendimento}>
            <div class="firstAtendimento">
                <lightning-radio-group name="radiofirstAtendimento"
                          label="Primeiro atendimento?"
                          options={optionsYesNo}
                          value={isFirst}
                          type="radio">
                </lightning-radio-group>
            </div>
        </template>

        <div class="date">
            <lightning-input type="date" 
                    name="inputDate" 
                    label="Enter a date">
            </lightning-input>
        </div>
        
        <div class="time">
            <lightning-input type="time" 
            name="inputTime" 
            label="Enter a time">
            </lightning-input>
        </div>

        <template if:true={enableTeleconsulta}>
            <div class="teleconsulta">
                <lightning-radio-group name="radioteleconsulta"
                          label="Teleconsulta"
                          options={optionsYesNo}
                          value={haveTeleconsulta}
                          type="radio">
                </lightning-radio-group>
            </div>
        </template>

        <template if:true={perfil}>
            <div class="comboBoxGroup">
                <lightning-combobox name="progress"
                        label="Status"
                        value={value}
                        placeholder="Select Progress"
                        options={optionsInput}
                        onchange={handleChange}>
                </lightning-combobox>

                <p class="custonSpace"></p>

                <lightning-combobox name="progress"
                        label="Status"
                        value={value}
                        placeholder="Select Progress"
                        options={optionsInput}
                        onchange={handleChange} 
                        disabled={testeDisabled}
                        step=2>
                </lightning-combobox>

                <p class="custonSpace"></p>

                <lightning-combobox name="progress"
                        label="Status"
                        value={value}
                        placeholder="Select Progress"
                        options={optionsInput}
                        onchange={handleChange}
                        step=3>
                </lightning-combobox>

                <p class="custonSpace"></p>

                <lightning-combobox name="progress"
                        label="Status"
                        value={value}
                        placeholder="Select Progress"
                        options={optionsInput}
                        onchange={handleChange} >
                </lightning-combobox>

                <p class="custonSpace"></p>

                <lightning-combobox name="progress"
                        label="Status"
                        value={value}
                        placeholder="Select Progress"
                        options={optionsInput}
                        onchange={handleChange} >
                </lightning-combobox>

            </div>
        </template>

        <div class="footer"></div>
    </div>  
</template>

###template###

###CSS###

.container{
    margin-left: 14px;
    background-color: rgb(255, 255, 255);
    --lwc-colorTextIconDefault: rgb(255, 94, 0);
    --sds-c-radio-mark-color-foreground:rgb(255, 94, 0);
    --sds-c-radio-color-border-checked: rgb(255, 94, 0);
    --sds-c-radio-shadow-focus: 0 0 3px rgb(255, 94, 0);
}

.custonSpace {
    height:13px;
}


.firstAtendimento {
    margin-left: 24px;
    padding-left: 24px;
    padding-top: 20px;
    --lwc-fontSize3: 1rem;
    font-weight: 500;
    --lwc-squareIconMediumContent: 1.5rem;

}

.date{
    display: inline-block;
    height: 47px;
    width: 20%;
    --lwc-formLabelFontSize: 1rem;
    margin-top: 0.8rem;
    margin-left: 24px;
    margin-bottom: 0.8rem;
    padding-left: 24px;
    --lwc-heightInput : 47px;
    --lwc-fontSize3: 1rem;
    --lwc-squareIconMediumContentAlt: 1.5rem;
    
}

.time{
    display: inline-block;
    height: 47px;
    width: 20%;
    --lwc-formLabelFontSize: 1rem;
    margin-top: 0.8rem;
    margin-left: 10px;
    margin-bottom: 0.8rem;
    padding-left: 24px;
    --lwc-heightInput : 47px;
    --lwc-fontSize3: 1rem;
    
}

.teleconsulta {
    display: inline-block;
    margin-left: 10px;
    padding-left: 24px;
    --lwc-fontSize3: 1rem;
    font-weight: 500;
    --lwc-squareIconMediumContent: 1.5rem;


}

.comboBoxGroup {
    margin-left: 24px;
    padding-left: 24px;
    margin-top: 20px;
    --lwc-heightInput : 47px;
    --lwc-fontSize3: 1rem;
    max-width: 60%;
}

.footer{
    bottom: auto;
    min-height: 100px;
}

###CSS###

###JS###

    firstAtendimento = true;
    enableTeleconsulta = true;
    perfil = true;
    isFirst = '';
    haveTeleconsulta = '';

    get optionsYesNo() {
        return [
            { label: 'Sim', value: 'true' },
            { label: 'Não', value: 'false' },
        ];
    }

    get optionsInput() {
        return [
            { label: 'New', value: 'new' },
            { label: 'In Progress', value: 'inProgress' },
            { label: 'Finished', value: 'finished' },
        ];
    }


###JS###

```

