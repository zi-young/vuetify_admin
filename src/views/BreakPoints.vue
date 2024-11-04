<template>
    <v-container class="grey lighten-3">
        <v-dialog 
            v-model="dialog"
            max-width="500"
        >
        <template v-slot:activator="{ props: activatorProps }">
            <v-btn
            v-bind="activatorProps"
            color="surface-variant"
            text="Open Dialog"
            variant="flat"
            ></v-btn>
        </template>

        <template v-slot:default="{ isActive }">
            <v-card title="Dialog">
            <v-card-text>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
            </v-card-text>

            <v-card-actions>
                <v-spacer></v-spacer>

                <v-btn
                text="Close Dialog"
                @click="isActive.value = false"
                ></v-btn>
            </v-card-actions>
            </v-card>
        </template>
        </v-dialog>
        <v-card class="mt-5">
            <v-card-title>
                $vuetify.breakpoint.name: {{ $vuetify.breakpoint.mobile }} {{ $vuetify.breakpoint.mobileBreakpoint }}
                <!-- 사이즈 확인 속성 -->
            </v-card-title>
            <v-card
                class="pa-3"
                outlined
                :height="height"
            >
                콘텐츠
            </v-card>
            <div class="text-center pa-4">
            <v-btn @click="dialog = true">
            Open Dialog
            </v-btn>

            <v-dialog
            v-model="dialog"
            width="auto"
            >
            <v-card
                max-width="400"
                prepend-icon="mdi-update"
                text="Your application will relaunch automatically after the update is complete."
                title="Update in progress"
            >
                <template v-slot:actions>
                <v-btn
                    class="ms-auto"
                    text="Ok"
                    @click="dialog = false"
                ></v-btn>
                </template>
            </v-card>
            </v-dialog>
        </div>
        </v-card>
    </v-container>
</template>
<script>
export default {
    data() {
        return {
            dialog: false,
        }
    },
    computed: {
        height() {
            switch (this.$vuetify.breakpoint.name) {
                case 'xs':return 100
                case 'sm': return 200
                case 'md': return 300
                case 'lg': return 400
                default: return 500
            }
        }
    }
}
</script>
<style lang="">
    
</style>