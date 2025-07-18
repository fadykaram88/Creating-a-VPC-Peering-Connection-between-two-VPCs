
# Project 8: Creating a VPC Peering Connection Between Two VPCs

> **Note:** VPC Peering is a one-to-one networking connection between two VPCs that enables you to route the traffic between them privately. This allows instances in both VPCs to communicate with each other.

> **Note:** You can create two VPCs by following the steps in **Project 3**.

---

## Task 1: Create VPC Peering

1. In the AWS Console, search for **VPC** and choose **Peering connections** from the left menu.
2. Click **Create Peering Connection**.
   - **Name (optional):** Lab-Peer
   - **VPC ID (Requester):** Lab VPC
   - **VPC ID (Accepter):** Shared VPC
3. Click **Create Peering Connection**.

> **Note:** Normally, you must wait for the acceptance from the owner of the other VPC. But since you are the owner of both VPCs in this project, you can accept the request manually.

4. Choose **Actions** → **Accept Request**.

---

## Task 2: Configure Route Tables

### Configure Lab VPC Route Table

5. In the left menu, choose **Route Tables**.
6. Select **Lab Public Route Table** (for Lab VPC).
7. Open the **Routes** tab → click **Edit routes** → **Add route**:
   - **Destination:** `10.5.0.0/16`
   - **Target:** Peering Connection → select `pcx-...` that represents Lab Peer.
8. Click **Save changes**.

### Configure Shared VPC Route Table

9. Return to **Route Tables** and choose **Shared-VPC Route Table**.
10. Open the **Routes** tab → click **Edit routes** → **Add route**:
    - **Destination:** `10.0.0.0/16`
    - **Target:** Peering Connection → select `Lab Peer` value.
11. Click **Save changes**.

---

## Task 3: Enable VPC Flow Logs

> Set up VPC Flow Logs to monitor the network traffic between the VPCs.

12. In the left menu, go to **Your VPCs** → select **Shared VPC**.
13. Open the **Flow Logs** tab → click **Create Flow Log**:
    - **Name (optional):** SharedVPCLogs
    - **Maximum aggregation interval:** 1 minute
    - **Destination:** Send to CloudWatch Logs
    - **Destination Log Group:** ShareVPCFlowLogs
    - **IAM Role:** `vpc-flow-logs-Role`
14. Click **Create Flow Log**.

15. Inside **Your VPCs**, select **Shared VPC** → open **Flow Tags** → click the link under **Destination name** to view the CloudWatch Log Group.

---

## Final Notes

- I hope this project was simple to understand.
- Goodbye and see you in the next project! 🚀
