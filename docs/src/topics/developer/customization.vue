<component class="view-page">
    <h1>Customization</h1>

    <h2>Branding</h2>
    <p>
        To start customizing a brand, the first thing you want to do is to add your brand
        (e.g. <b>yourbrand</b>) in the <em>brands</em> section of <code>.ca11rc</code>
        by copying the <em>ca11</em> brand schema. Then copy the <code>src/brand/ca11</code>
        directory and its content to <code>src/brand/yourbrand</code>.
        Make sure that the name exactly matches the key you use in the brands section of <code>.ca11rc</code>.
        Overwrite the images in <code>src/brand/yourbrand/img</code> with your own. The color palette of
        <em>yourbrand</em> can be used to match your branding identity.
    </p>

    <p>
        Please <b>do not</b> publish under the same name or a different name with a branding
        that already exists. If you want to create your own brand, come up with
        a unique branding name for your CA11 clone, a unique color scheme and create branded
        versions of the images in <em>/src/brand/ca11/img</em>.
    </p>

    <h2>Plugins</h2>
    <p>
        In <code>.ca11rc</code> there is a section that references plugins which
        are used to add custom functionality to your build. The <em>Ca11</em> build is
        quite minimal. A different build with a more extensive plugin setup could look like:
    </p>

<pre v-highlightjs><code class="json">"plugins": {
    "builtin": {
        "availability": {
            "addons": {
                "bg": ["ca11-addon-availability-customname"],
                "fg": ["ca11-addon-availability-customname"],
                "i18n": ["ca11-addon-availability-customname"]
            }
        },
        "contacts": {
            "i18n": ["ca11-provider-contacts-customname"],
            "providers": ["ca11-provider-contacts-customname"]
        }
    },
    "custom": {
        "queues": {
            "name": "ca11-mod-queues-customname",
            "parts": ["bg", "fg", "i18n"]
        }
    }
}
</code></pre>
    <p>
        The <em>builtin</em> plugins are existing core plugins, that can be extended
        by using a custom <i>adapter</i>, a <i>provider</i> or an <i>addon</i>.
        This system is still in flux, so it doesn't come with much documentation.
        The sourcecode is your friend.
    </p>

</component>
