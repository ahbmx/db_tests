```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Storage Provisioning</title>

    <style>
        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            font-family: Arial, Helvetica, sans-serif;
            background: #f4f6f8;
            color: #1f2937;
        }

        .container {
            max-width: 1200px;
            margin: 30px auto;
            padding: 0 20px;
        }

        .header {
            margin-bottom: 25px;
        }

        .header h1 {
            margin: 0 0 6px;
            font-size: 28px;
        }

        .header p {
            margin: 0;
            color: #6b7280;
        }

        .card {
            background: white;
            border-radius: 10px;
            padding: 25px;
            margin-bottom: 20px;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.06);
        }

        .card h2 {
            margin-top: 0;
            font-size: 20px;
            border-bottom: 1px solid #e5e7eb;
            padding-bottom: 12px;
        }

        .form-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 18px 24px;
        }

        .form-group {
            display: flex;
            flex-direction: column;
        }

        .form-group.full {
            grid-column: 1 / -1;
        }

        label {
            font-weight: 600;
            margin-bottom: 7px;
            font-size: 14px;
        }

        input,
        select,
        textarea {
            width: 100%;
            padding: 10px 12px;
            border: 1px solid #d1d5db;
            border-radius: 6px;
            font-size: 14px;
            background: white;
        }

        input:focus,
        select:focus,
        textarea:focus {
            outline: none;
            border-color: #2563eb;
            box-shadow: 0 0 0 2px rgba(37, 99, 235, 0.1);
        }

        .site-selection {
            display: flex;
            gap: 15px;
            margin-bottom: 20px;
        }

        .site-checkbox {
            display: flex;
            align-items: center;
            gap: 8px;
            padding: 12px 18px;
            border: 1px solid #d1d5db;
            border-radius: 6px;
            cursor: pointer;
            background: #fff;
        }

        .site-checkbox:hover {
            background: #f9fafb;
        }

        .site-checkbox input {
            width: auto;
        }

        .site-section {
            border: 1px solid #d1d5db;
            border-radius: 8px;
            margin-bottom: 20px;
            overflow: hidden;
        }

        .site-header {
            background: #1f4e78;
            color: white;
            padding: 14px 18px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .site-header h3 {
            margin: 0;
            font-size: 17px;
        }

        .site-body {
            padding: 20px;
        }

        .server-card {
            border: 1px solid #e5e7eb;
            border-radius: 8px;
            padding: 18px;
            margin-bottom: 15px;
            background: #fafafa;
        }

        .server-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
        }

        .server-header h4 {
            margin: 0;
            font-size: 16px;
        }

        .button {
            border: none;
            border-radius: 6px;
            padding: 10px 16px;
            font-size: 14px;
            cursor: pointer;
            font-weight: 600;
        }

        .button-primary {
            background: #2563eb;
            color: white;
        }

        .button-primary:hover {
            background: #1d4ed8;
        }

        .button-secondary {
            background: #e5e7eb;
            color: #374151;
        }

        .button-secondary:hover {
            background: #d1d5db;
        }

        .button-danger {
            background: #fee2e2;
            color: #b91c1c;
        }

        .button-danger:hover {
            background: #fecaca;
        }

        .button-success {
            background: #16a34a;
            color: white;
        }

        .button-success:hover {
            background: #15803d;
        }

        .actions {
            display: flex;
            justify-content: flex-end;
            gap: 12px;
            margin-top: 25px;
        }

        .empty-message {
            color: #6b7280;
            text-align: center;
            padding: 20px;
        }

        .total-box {
            background: #eff6ff;
            border: 1px solid #bfdbfe;
            border-radius: 6px;
            padding: 12px 15px;
            margin-top: 15px;
            font-size: 14px;
        }

        .success-message {
            display: none;
            background: #dcfce7;
            border: 1px solid #86efac;
            color: #166534;
            padding: 15px;
            border-radius: 6px;
            margin-bottom: 20px;
        }

        @media (max-width: 700px) {
            .form-grid {
                grid-template-columns: 1fr;
            }

            .site-selection {
                flex-direction: column;
            }
        }
    </style>
</head>

<body>

<div class="container">

    <div class="header">
        <h1>Storage Provisioning</h1>
        <p>Create a new storage provisioning record.</p>
    </div>

    <div id="successMessage" class="success-message">
        Provisioning submitted successfully.
    </div>

    <!-- GENERAL INFORMATION -->

    <div class="card">

        <h2>Provisioning Information</h2>

        <div class="form-grid">

            <div class="form-group">
                <label for="provisioningType">
                    Provisioning Type *
                </label>

                <select id="provisioningType" required>
                    <option value="">Select...</option>
                    <option value="New Server">New Server</option>
                    <option value="Expansion">Expansion</option>
                    <option value="Storage Increase">Storage Increase</option>
                    <option value="Migration">Migration</option>
                    <option value="Other">Other</option>
                </select>
            </div>


            <div class="form-group">
                <label for="assignee">
                    Assignee
                </label>

                <input
                    type="text"
                    id="assignee"
                    placeholder="Storage team member">
            </div>


            <div class="form-group">
                <label for="provisionedDate">
                    Provisioned Date *
                </label>

                <input
                    type="date"
                    id="provisionedDate"
                    required>
            </div>


            <div class="form-group">
                <label for="eventType">
                    Event Type
                </label>

                <select id="eventType">
                    <option value="">Select...</option>
                    <option value="Standard">Standard</option>
                    <option value="Emergency">Emergency</option>
                    <option value="Planned">Planned</option>
                    <option value="Other">Other</option>
                </select>
            </div>


            <div class="form-group">
                <label for="projectType">
                    Project Type
                </label>

                <select id="projectType">
                    <option value="">Select...</option>
                    <option value="Infrastructure">Infrastructure</option>
                    <option value="Application">Application</option>
                    <option value="Migration">Migration</option>
                    <option value="Other">Other</option>
                </select>
            </div>


            <div class="form-group">
                <label for="businessApp">
                    Business App
                </label>

                <select id="businessApp">
                    <option value="">Select...</option>
                    <option value="SAP">SAP</option>
                    <option value="Oracle">Oracle</option>
                    <option value="CRM">CRM</option>
                    <option value="Data Warehouse">Data Warehouse</option>
                    <option value="Other">Other</option>
                </select>
            </div>


            <div class="form-group">
                <label for="chg">
                    CHG
                </label>

                <input
                    type="text"
                    id="chg"
                    placeholder="CHG0012345">
            </div>


            <div class="form-group">
                <label for="incident">
                    INCIDENT
                </label>

                <input
                    type="text"
                    id="incident"
                    placeholder="INC0012345">
            </div>


            <div class="form-group full">
                <label for="requestor">
                    Requestor
                </label>

                <input
                    type="text"
                    id="requestor"
                    placeholder="Requestor name">
            </div>

        </div>
    </div>


    <!-- SITE SELECTION -->

    <div class="card">

        <h2>Sites</h2>

        <p>
            Select the sites where resources are being provisioned.
        </p>

        <div class="site-selection">

            <label class="site-checkbox">
                <input
                    type="checkbox"
                    value="CL"
                    onchange="toggleSite('CL')">

                CL
            </label>


            <label class="site-checkbox">
                <input
                    type="checkbox"
                    value="TL"
                    onchange="toggleSite('TL')">

                TL
            </label>

        </div>

        <div id="sitesContainer">

            <div class="empty-message">
                Select CL and/or TL above.
            </div>

        </div>

    </div>


    <!-- ACTIONS -->

    <div class="actions">

        <button
            type="button"
            class="button button-secondary"
            onclick="resetForm()">

            Cancel
        </button>

        <button
            type="button"
            class="button button-success"
            onclick="submitForm()">

            Submit Provisioning
        </button>

    </div>

</div>


<script>

    /*
     * Keep track of the servers/resources
     * entered for each site.
     */

    const siteData = {
        CL: [],
        TL: []
    };


    /*
     * Site selection
     */

    function toggleSite(site) {

        const checkbox =
            document.querySelector(
                `input[value="${site}"]`
            );

        const container =
            document.getElementById("sitesContainer");

        if (checkbox.checked) {

            if (siteData[site].length === 0) {

                addServer(site);

            }

        } else {

            siteData[site] = [];

            const section =
                document.getElementById(
                    `site-${site}`
                );

            if (section) {
                section.remove();
            }
        }

        updateEmptyMessage();
    }


    /*
     * Add a server/resource to a site
     */

    function addServer(site) {

        const id =
            Date.now() +
            Math.floor(Math.random() * 1000);

        siteData[site].push({
            id: id,
            server: "",
            physical_virtual: "",
            os: "",
            vm_lun: "",
            rdm_vmdk: "",
            actual_gb: ""
        });

        renderSite(site);
    }


    /*
     * Remove a server
     */

    function removeServer(site, id) {

        siteData[site] =
            siteData[site].filter(
                resource => resource.id !== id
            );

        renderSite(site);
    }


    /*
     * Render a site section
     */

    function renderSite(site) {

        const container =
            document.getElementById("sitesContainer");

        let section =
            document.getElementById(`site-${site}`);

        if (!section) {

            section =
                document.createElement("div");

            section.id = `site-${site}`;
            section.className = "site-section";

            container.appendChild(section);
        }


        let html = `
            <div class="site-header">

                <h3>${site} Site</h3>

                <span>
                    ${siteData[site].length}
                    server(s)
                </span>

            </div>

            <div class="site-body">
        `;


        if (siteData[site].length === 0) {

            html += `
                <div class="empty-message">
                    No servers added yet.
                </div>
            `;

        } else {

            siteData[site].forEach(
                (resource, index) => {

                    html += `

                    <div
                        class="server-card"
                        data-id="${resource.id}">

                        <div class="server-header">

                            <h4>
                                Server ${index + 1}
                            </h4>

                            <button
                                type="button"
                                class="button button-danger"
                                onclick="removeServer(
                                    '${site}',
                                    ${resource.id}
                                )">

                                Remove

                            </button>

                        </div>


                        <div class="form-grid">

                            <div class="form-group">

                                <label>
                                    Server
                                </label>

                                <input
                                    type="text"
                                    value="${escapeHtml(resource.server)}"
                                    onchange="updateResource(
                                        '${site}',
                                        ${resource.id},
                                        'server',
                                        this.value
                                    )"
                                    placeholder="Server name">

                            </div>


                            <div class="form-group">

                                <label>
                                    Physical / Virtual
                                </label>

                                <select
                                    onchange="updateResource(
                                        '${site}',
                                        ${resource.id},
                                        'physical_virtual',
                                        this.value
                                    )">

                                    <option value="">
                                        Select...
                                    </option>

                                    <option
                                        value="Physical"
                                        ${resource.physical_virtual === "Physical"
                                            ? "selected"
                                            : ""}>
                                        Physical
                                    </option>

                                    <option
                                        value="Virtual"
                                        ${resource.physical_virtual === "Virtual"
                                            ? "selected"
                                            : ""}>
                                        Virtual
                                    </option>

                                </select>

                            </div>


                            <div class="form-group">

                                <label>
                                    Operating System
                                </label>

                                <select
                                    onchange="updateResource(
                                        '${site}',
                                        ${resource.id},
                                        'os',
                                        this.value
                                    )">

                                    <option value="">
                                        Select...
                                    </option>

                                    <option
                                        value="Windows Server 2019"
                                        ${resource.os === "Windows Server 2019"
                                            ? "selected"
                                            : ""}>
                                        Windows Server 2019
                                    </option>

                                    <option
                                        value="Windows Server 2022"
                                        ${resource.os === "Windows Server 2022"
                                            ? "selected"
                                            : ""}>
                                        Windows Server 2022
                                    </option>

                                    <option
                                        value="RHEL 8"
                                        ${resource.os === "RHEL 8"
                                            ? "selected"
                                            : ""}>
                                        RHEL 8
                                    </option>

                                    <option
                                        value="RHEL 9"
                                        ${resource.os === "RHEL 9"
                                            ? "selected"
                                            : ""}>
                                        RHEL 9
                                    </option>

                                    <option
                                        value="SUSE Linux"
                                        ${resource.os === "SUSE Linux"
                                            ? "selected"
                                            : ""}>
                                        SUSE Linux
                                    </option>

                                    <option
                                        value="AIX"
                                        ${resource.os === "AIX"
                                            ? "selected"
                                            : ""}>
                                        AIX
                                    </option>

                                    <option
                                        value="Other"
                                        ${resource.os === "Other"
                                            ? "selected"
                                            : ""}>
                                        Other
                                    </option>

                                </select>

                            </div>


                            <div class="form-group">

                                <label>
                                    VM / LUN
                                </label>

                                <input
                                    type="text"
                                    value="${escapeHtml(resource.vm_lun)}"
                                    onchange="updateResource(
                                        '${site}',
                                        ${resource.id},
                                        'vm_lun',
                                        this.value
                                    )"
                                    placeholder="Informational">

                            </div>


                            <div class="form-group">

                                <label>
                                    RDM / VMDK
                                </label>

                                <input
                                    type="text"
                                    value="${escapeHtml(resource.rdm_vmdk)}"
                                    onchange="updateResource(
                                        '${site}',
                                        ${resource.id},
                                        'rdm_vmdk',
                                        this.value
                                    )"
                                    placeholder="Informational">

                            </div>


                            <div class="form-group">

                                <label>
                                    Actual GB
                                </label>

                                <input
                                    type="number"
                                    min="0"
                                    step="0.01"
                                    value="${escapeHtml(resource.actual_gb)}"
                                    onchange="updateResource(
                                        '${site}',
                                        ${resource.id},
                                        'actual_gb',
                                        this.value
                                    )"
                                    placeholder="0">

                            </div>

                        </div>

                    </div>

                    `;
                }
            );
        }


        html += `

                <button
                    type="button"
                    class="button button-primary"
                    onclick="addServer('${site}')">

                    + Add Server

                </button>

                <div class="total-box">

                    Total storage for ${site}:

                    <strong>
                        ${calculateSiteTotal(site).toLocaleString()}
                        GB
                    </strong>

                </div>

            </div>
        `;


        section.innerHTML = html;

        updateEmptyMessage();
    }


    /*
     * Update resource data
     */

    function updateResource(
        site,
        id,
        field,
        value
    ) {

        const resource =
            siteData[site].find(
                item => item.id === id
            );

        if (resource) {

            resource[field] = value;

        }

        if (field === "actual_gb") {

            renderSite(site);

        }
    }


    /*
     * Calculate total GB for a site
     */

    function calculateSiteTotal(site) {

        return siteData[site].reduce(
            (total, resource) => {

                return total +
                    (parseFloat(resource.actual_gb) || 0);

            },
            0
        );
    }


    /*
     * Calculate total GB across all sites
     */

    function calculateTotalGB() {

        return (
            calculateSiteTotal("CL") +
            calculateSiteTotal("TL")
        );
    }


    /*
     * Empty site message
     */

    function updateEmptyMessage() {

        const container =
            document.getElementById("sitesContainer");

        const hasSites =
            document.getElementById("site-CL") ||
            document.getElementById("site-TL");

        const empty =
            container.querySelector(".empty-message");

        if (!hasSites) {

            if (!empty) {

                const message =
                    document.createElement("div");

                message.className =
                    "empty-message";

                message.textContent =
                    "Select CL and/or TL above.";

                container.appendChild(message);
            }

        } else if (empty) {

            empty.remove();
        }
    }


    /*
     * Submit form
     */

    function submitForm() {

        const provisioningType =
            document.getElementById(
                "provisioningType"
            ).value;

        const provisionedDate =
            document.getElementById(
                "provisionedDate"
            ).value;


        if (!provisioningType) {

            alert(
                "Please select a provisioning type."
            );

            return;
        }


        if (!provisionedDate) {

            alert(
                "Please enter the provisioned date."
            );

            return;
        }


        const selectedSites =
            Object.keys(siteData)
                .filter(
                    site =>
                        siteData[site].length > 0
                );


        if (selectedSites.length === 0) {

            alert(
                "Please select at least one site."
            );

            return;
        }


        /*
         * This is the structure that can be
         * sent to your backend API.
         */

        const formData = {

            provisioning: {

                provisioning_type:
                    provisioningType,

                assignee:
                    document.getElementById(
                        "assignee"
                    ).value,

                provisioned_date:
                    provisionedDate,

                event_type:
                    document.getElementById(
                        "eventType"
                    ).value,

                project_type:
                    document.getElementById(
                        "projectType"
                    ).value,

                chg:
                    document.getElementById(
                        "chg"
                    ).value,

                incident:
                    document.getElementById(
                        "incident"
                    ).value,

                business_app:
                    document.getElementById(
                        "businessApp"
                    ).value,

                requestor:
                    document.getElementById(
                        "requestor"
                    ).value
            },

            resources: [

                ...siteData.CL.map(
                    resource => ({
                        ...resource,
                        site: "CL"
                    })
                ),

                ...siteData.TL.map(
                    resource => ({
                        ...resource,
                        site: "TL"
                    })
                )

            ]

        };


        console.log(
            "FORM DATA:",
            formData
        );


        /*
         * For now, show what would be
         * sent to the server.
         */

        alert(
            "Provisioning ready to submit.\n\n" +
            "Total Storage: " +
            calculateTotalGB().toLocaleString() +
            " GB\n\n" +
            "See browser console for JSON."
        );


        document.getElementById(
            "successMessage"
        ).style.display = "block";
    }


    /*
     * Reset
     */

    function resetForm() {

        if (
            !confirm(
                "Are you sure you want to clear this form?"
            )
        ) {
            return;
        }

        window.location.reload();
    }


    /*
     * Prevent HTML injection when displaying
     * text values inside the form.
     */

    function escapeHtml(value) {

        if (!value) {
            return "";
        }

        return String(value)
            .replace(/&/g, "&amp;")
            .replace(/</g, "&lt;")
            .replace(/>/g, "&gt;")
            .replace(/"/g, "&quot;")
            .replace(/'/g, "&#039;");
    }


    /*
     * Default today's date.
     */

    document.getElementById(
        "provisionedDate"
    ).value =
        new Date()
            .toISOString()
            .split("T")[0];

</script>

</body>
</html>
```
