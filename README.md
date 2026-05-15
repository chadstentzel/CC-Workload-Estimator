# Cortex Cloud License Calculator

Web-based calculator for determining Cortex Cloud workload license requirements based on Palo Alto Networks metering guide.

## Files

### Calculators

- **cortex-license-calculator-v1.html** - Manual entry version
  - All workload types must be entered manually
  - Includes PDF export functionality
  - Separates Posture vs Runtime licenses

- **cortex-license-calculator-v2.html** - Upload-enabled version
  - All features from v1
  - PLUS: Upload sizing script output for automatic population
  - Supports AWS, Azure, and GCP sizing script outputs

### Sample Files

Test files for v2 upload functionality:
- **sample-aws-output.txt** - Sample AWS workload sizing output
- **sample-azure-output.txt** - Sample Azure workload sizing output
- **sample-gcp-output.txt** - Sample GCP workload sizing output

## Usage

### V1 - Manual Entry
1. Open `cortex-license-calculator-v1.html` in a web browser
2. Enter workload counts manually for each resource type
3. View calculated Posture and Runtime license totals
4. Export results to PDF if needed

### V2 - With Upload
1. Open `cortex-license-calculator-v2.html` in a web browser
2. Either:
   - Upload output from sizing scripts (AWS/Azure/GCP) OR
   - Enter workload counts manually
3. View calculated Posture and Runtime license totals
4. Export results to PDF if needed

## License Types

### Posture Only (Vulnerability & Misconfiguration)
- Agentless security scanning
- Available for all workload types
- Provides CSPM, CIEM, ASPM, DSPM, AI-SPM, Cloud ASM, KSPM, CI/CD Posture Management

### Runtime (Agent Required)
- Agent-based runtime protection
- Only available for compute resources (VMs, CaaS, Serverless Functions)
- Includes all Posture capabilities PLUS CWP, WAAS, and CDR

## Workload Metering Ratios

| Workload Type | Billable Unit per 1 Workload |
|---------------|------------------------------|
| VMs (not running containers) | 1 VM |
| VMs (running containers) | 1 VM |
| CaaS (Container as a Service) | 10 Managed Containers |
| Serverless Functions | 25 Serverless Functions |
| Cloud Buckets | 10 Cloud Buckets |
| Managed Cloud Database (PaaS) | 2 PaaS Databases |
| DBaaS (Database as a Service) | 1 TB Stored |
| SaaS Users | 10 SaaS Users |
| Cloud ASM - Unmanaged Services | 4 Unmanaged Assets |
| Container Images in Registries | 10 Container Image Scans (beyond free quota) |

## Sizing Scripts

For automated workload discovery, use the sizing scripts located at:
`C:\Users\cstentzel\Documents\Code\CC Sizing Script\cc-workload-sizing-main`

Available for:
- AWS - `AWS/cc-workload-sizing-aws.sh`
- Azure - `AZURE/cc-workload-sizing-azure.sh`
- GCP - `GCP/cc-workload-sizing-gcp.sh`

Run these scripts in your cloud environment and upload the output to v2 of the calculator for automatic field population.

## Features

- ✅ Accurate workload to license conversion
- ✅ Separate Posture and Runtime license tracking
- ✅ PDF export for sharing results
- ✅ Upload sizing script output (v2)
- ✅ Automatic workload calculation
- ✅ Detailed breakdown by resource type
- ✅ Responsive design for mobile/desktop

## Technical Details

Built with:
- Pure HTML/CSS/JavaScript
- jsPDF library for PDF generation
- No server-side components required
- Runs entirely in the browser

---

*For questions about Cortex Cloud licensing, contact your Palo Alto Networks account team.*
