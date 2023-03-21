<template>
    <v-switch :label="`${tableTheme}`" color="black" v-model="tableTheme" :true-value="darkModeString"
        :false-value="lightModeString" inset hide-details></v-switch>

    <v-responsive class="mx-auto" max-width="344">
        <v-text-field v-model="searchString" label="Search" placeholder="Enter Search String"
            hide-details="auto"></v-text-field>
    </v-responsive>

    <v-container class="fill-height">
        <v-responsive class="d-flex align-center text-center fill-height">
            <v-table :theme="getTheme()">
                <thead>
                    <tr>
                        <th class="text-center">
                            Image
                        </th>
                        <th class="text-center">
                            Year
                        </th>
                        <th class="text-center">
                            Manufacturer
                        </th>
                        <th class="text-center">
                            Model
                        </th>
                        <th class="text-center">
                            Color
                        </th>
                        <th class="text-center">
                            Power
                        </th>

                        <th class="text-center">
                            Displacement
                        </th>
                        <th class="text-center">
                            Description
                        </th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="bike in filteredSearchList()" :key="bike.model">
                        <td>
                            <v-img v-if="bike.model == 'F 750 GS'" contain height="100" src="@/assets/F750GS.svg"
                                @click="clickedF750GS" />

                            <v-img v-if="bike.model == 'Monster 821 Stealth'" contain height="100"
                                src="@/assets/Monster821Stealth.svg" @click="clickedMonster821Stealth" />

                            <v-img v-if="bike.model == 'Panigale V4'" contain height="100" src="@/assets/PanigaleV4.svg"
                                @click="clickedPanigaleV4" />

                            <v-img v-if="bike.model == 'Scout Bobber'" contain height="100" src="@/assets/ScoutBobber.svg"
                                @click="clickedScoutBobber" />
                        </td>
                        <td>{{ bike.year }}</td>
                        <td>{{ bike.manufacturer }}</td>
                        <td>{{ bike.model }}</td>
                        <td>{{ bike.color }}</td>
                        <td>{{ bike.power }}</td>
                        <td>{{ bike.displacement }}</td>
                        <td>{{ bike.description }}</td>
                    </tr>
                </tbody>
            </v-table>
        </v-responsive>
    </v-container>
</template>

<script lang="ts" setup>

import { ref, onMounted } from 'vue';

const searchString = ref("");

const lightModeString = "Light Mode";
const darkModeString = "Dark Mode";

//on reload default mode is light mode
const tableTheme = ref(lightModeString);

class Bikes {
    bikes: Bike[] = [];
    constructor() {
        let bike1 = new Bike("Ducati", "Monster 821 Stealth", "109 hp (80 kW)", "The Monster 821 pays homage to the legacy of the Monster 900, which over 25 years ago revolutionized the motorcycle world. Agile and featuring sporty performance, it was designed for maximum riding enjoyment, at all times and in all conditions.  The Monster 821 range has been rejuvenated with a new stealth version: matte black livery, updated graphics and front fairing give a unique character to the naked Ducati par excellence.", "Stealth Black", "821 cc", "2020");
        let bike2 = new Bike("BMW", "F 750 GS", "77 hp (at 7,500 rpm)", "The BMW F 750 GS is your ticket to adventure. With this balanced Enduro all-rounder, you can master all paths and expand your horizons. The F 750 GS gives you more power, more comfort, more spirit of GS. Feel the strong-charactered engine and enjoy the ease of handling of the F 750 GS. While you're off discovering the world, you have the bike safely under control with the Automatic Stability Control (ASC) and ABS. With the additional option Connectivity, the 6.5 inch TFT-display boasts many features including navigation and smartphone connectivity.", "Austin Yellow Metallic", "853 cc", "2020");
        let bike3 = new Bike("Indian", "Scout Bobber", "100 hp", "Stripped down and blacked out with an aggressive stance and raw power, the Scout Bobber is a modern take on the iconic bobber style.", "Black", "1,133 cc", "2020");
        let bike4 = new Bike("Ducati", "Panigale V4", "157.5 kW (214 hp)", "The 2020 version of the Panigale V4 boosts performance even further and takes track riding to the next level for amateurs and pros alike.", "Ducati Red", "1,103 cc", "2020");
        this.bikes.push(bike1);
        this.bikes.push(bike2);
        this.bikes.push(bike3);
        this.bikes.push(bike4);
    }
}

class Bike {
    manufacturer: string;
    model: string;
    power: string;
    description: string;
    color: string;
    displacement: string;
    year: string;
    constructor(manufacturer: string, model: string, power: string, description: string, color: string, displacement: string, year: string) {
        this.manufacturer = manufacturer;
        this.model = model;
        this.power = power;
        this.description = description;
        this.color = color;
        this.displacement = displacement;
        this.year = year;
    }
}

let bikes = new Bikes();

function clickedF750GS() {
    console.log("clickedF750GS");
}

function clickedMonster821Stealth() {
    console.log("clickedMonster821Stealth");
}

function clickedPanigaleV4() {
    console.log("clickedPanigaleV4");
}

function clickedScoutBobber() {
    console.log("clickedScoutBobber");
}

function getTheme() {
    return tableTheme.value == darkModeString ? 'dark' : 'light';
}

function filteredSearchList() {

    //console.log(searchString.value);

    let searchResults = new Set<Bike>();

    //nested for loops, very undesirable, but okay for very small data set
    for (var bike of bikes.bikes) {
        Object.values(bike).forEach(val => {
            if (val.toLowerCase().includes(searchString.value.toLowerCase())) {
                searchResults.add(bike);
            }
        });
    }

    return searchResults;

}

onMounted(() => {
    console.log('MyGarage mounted.')
})

</script>
  