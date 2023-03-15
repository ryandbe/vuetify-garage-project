<template>
    <v-container class="fill-height">
        <v-responsive class="d-flex align-center text-center fill-height">
            <v-table theme="dark">
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
                    <tr>
                        <td>
                            <v-img contain height="100" src="@/assets/F750GS.svg" @click="clickedF750GS" />
                        </td>
                        <td>2020</td>
                        <td>BMW</td>
                        <td>F 750 GS</td>
                        <td>Austin Yellow Metallic</td>
                        <td>77 hp (at 7,500 rpm)</td>
                        <td>853 cc</td>
                        <td>The BMW F 750 GS is your ticket to adventure. With this balanced Enduro all-rounder, you can
                            master all paths and expand your horizons. The F 750 GS gives you more power, more comfort, more
                            spirit of GS. Feel the strong-charactered engine and enjoy the ease of handling of the F 750 GS.
                            While you're off discovering the world, you have the bike safely under control with the
                            Automatic Stability Control (ASC) and ABS. With the additional option Connectivity, the 6.5 inch
                            TFT-display boasts many features including navigation and smartphone connectivity.</td>
                    </tr>
                    <tr>
                        <td>
                            <v-img contain height="100" src="@/assets/Monster821Stealth.svg"
                                @click="clickedMonster821Stealth" />
                        </td>
                        <td>2020</td>
                        <td>Ducati</td>
                        <td>Monster 821 Stealth</td>
                        <td>Stealth Black</td>
                        <td>109 hp (80 kW)</td>
                        <td>821 cc</td>
                        <td>The Monster 821 pays homage to the legacy of the Monster 900, which over 25 years ago
                            revolutionized the motorcycle world. Agile and featuring sporty performance, it was designed for
                            maximum riding enjoyment, at all times and in all conditions. The Monster 821 range has been
                            rejuvenated with a new stealth version: matte black livery, updated graphics and front fairing
                            give a unique character to the naked Ducati par excellence.</td>
                    </tr>
                    <tr>
                        <td>
                            <v-img contain height="100" src="@/assets/PanigaleV4.svg" @click="clickedPanigaleV4" />
                        </td>
                        <td>2020</td>
                        <td>Ducati</td>
                        <td>Panigale V4</td>
                        <td>Ducati Red</td>
                        <td>157.5 kW (214 hp)</td>
                        <td>1,103 cc</td>
                        <td>The 2020 version of the Panigale V4 boosts performance even further and takes track riding to
                            the next level for amateurs and pros alike.</td>
                    </tr>
                    <tr>
                        <td>
                            <v-img contain height="100" src="@/assets/ScoutBobber.svg" @click="clickedScoutBobber" />
                        </td>
                        <td>2020</td>
                        <td>Indian</td>
                        <td>Scout Bobber</td>
                        <td>Black</td>
                        <td>100 hp</td>
                        <td>1,133 cc</td>
                        <td>Stripped down and blacked out with an aggressive stance and raw power, the Scout Bobber is a
                            modern take on the iconic bobber style.</td>
                    </tr>
                </tbody>
            </v-table>
        </v-responsive>
    </v-container>
</template>
  
<!-- <template>
    <v-card>
        <v-card-title>
            <v-text-field v-model="search" label="Search"></v-text-field>
        </v-card-title>
        <v-data-table :headers="headers" :items="records" :search="search">
            <template slot="items" slot-scope="props">
                <tr>
                    <td>{{ props.data.id }}</td>
                    <td>{{ props.item.description }}</td>
                    <td>{{ props.item.cost }}</td>
                </tr>
            </template>
        </v-data-table>
    </v-card>
</template> -->

<!-- <template>
    <v-data-table v-model="search" :headers="headers" :items="records" item-value="name" class="elevation-1">
        <template slot="items" slot-scope="props">
            <tr>
          <td>{{ props.item.id }}</td>
          <td>{{ props.item.description }}</td>
          <td>{{ props.item.cost }}</td>
        </tr>
            </template>
    
    </v-data-table>
</template> -->


<script lang="ts" setup>

console.log("My Garage test");

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

</script>
  