<script>
import { mapState } from "vuex";
export default {
    name: "Footer",
    components: {},
    props: {},
    data() {
        return {
            links: [
                {
                    label: "LinkedIn",
                    url: "https://www.linkedin.com/in/margueriteroth/",
                },
                {
                    label: "Instagram",
                    url: "https://instagram.com/marguer.ite/",
                },
                {
                    label: "Github",
                    url: "https://github.com/margueriteroth/",
                },
            ],
        };
    },
    computed: {
        ...mapState({
            infoDensity: state => state.infoDensity,
            themeColor: state => state.themeColor,
        }),
    },
    methods: {
        toggleInfoDensity() {
            let density = this.infoDensity == "low" ? "high" : "low";
            this.$store.dispatch("setInfoDensity", density);
        },
        toggleThemeColor() {
            let theme = this.themeColor == "light" ? "dark" : "light";
            this.$store.dispatch("setThemeColor", theme);
        },
    },
};
</script>

<template>
    <MaxWidth class="footer__container" size="xl">
        <!-- <MaxWidth size="m" class="footer">
            <div class="footer__left">
                <Link to="https://marguerite.io" do-open-in-new-tab alt="marguerite.io">
                <MargTitle size="xs" />
                </Link>
            </div>
            <div class="footer__right">
              
            </div>
        </MaxWidth> -->
    </MaxWidth>
</template>

<style lang="scss">
.footer {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    width: 100%;
    flex-wrap: wrap;

    &__container {
        position: relative;
        background: white;
    }

    &__left {
        width: 100%;
        border-top: 1px solid rgba(black, 0.2);
        padding-top: 2em;
        padding-bottom: 2em;
    }

    &__right {
        display: flex;
        width: 100%;
        gap: 2em;
        justify-content: flex-end;
        border-top: 1px solid rgba(black, 0.2);
        padding-top: 2em;
        padding-bottom: 2em;
        padding-left: 2em;

        .repo {
            display: flex;
            align-items: top;
            gap: 0.5em;
        }

        svg {
            width: 18px;
        }

        label {
            opacity: 0.5;
        }
    }

    p {
        font-size: 0.9rem;
        display: relative;

        &:first-of-type {
            margin-top: 0;
        }
    }
}
</style>
