<component class="c-main-status main-status" :class="classes()">

    <div class="status-indicators">
        <div class="status-indicator sig11 tooltip tooltip-right" :data-tooltip="tooltipSig11">
            <icon name="protocol-sig11" v-if="!sig11.enabled" class="disabled"/>
            <icon name="mute" v-else-if="!settings.webrtc.media.permission"/>
            <icon name="mute" v-else-if="!settings.webrtc.devices.ready"/>
            <icon name="spinner" v-else-if="sig11.status === 'loading'" class="spinner"/>
            <icon name="protocol-sig11" v-else/>
        </div>

        <div class="status-indicator sip tooltip tooltip-right" :data-tooltip="tooltipSip">
            <icon name="protocol-sip" v-if="!sip.enabled" class="disabled"/>
            <icon name="mute" v-else-if="!settings.webrtc.media.permission"/>
            <icon name="mute" v-else-if="!settings.webrtc.devices.ready"/>
            <icon name="spinner" v-else-if="sip.status === 'loading'" class="spinner"/>
            <icon name="protocol-sip" v-else/>
        </div>

        <Availability class="dnd-switch" />
    </div>


    <div class="menu-options">
        <!-- Popout link in WebExtension -->
        <div class="option" v-if="env.isExtension && !env.isPopout" @click="openPopoutView">
            <icon class="ext-tab" name="ext-tab"/>
        </div>

        <div class="option test-statusbar-settings" :class="{active: layer === 'settings'}" @click="setLayer('settings')">
            <icon class="settings" name="settings"/>
        </div>

        <div class="option" @click="logout">
            <icon name="logout"/>
        </div>

        <div class="option" :class="{active: layer === 'about'}" @click="setOverlay('about')">
            <icon name="help"/>
        </div>
    </div>
</component>
